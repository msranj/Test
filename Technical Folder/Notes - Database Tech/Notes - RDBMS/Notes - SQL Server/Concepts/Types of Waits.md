Troubleshooting THREADPOOL Waits: 

https://www.sqlpassion.at/archive/2011/10/25/troubleshooting-threadpool-waits/

Inside the Statistics Histogram & Density Vector: <https://www.sqlpassion.at/archive/2014/01/28/inside-the-statistics-histogram-density-vector/> 

SQL Server Quickie #21 – Wait Statistics: <https://www.sqlpassion.at/archive/author/siteadmin/page/43/> 

https://voiceofthedba.com/2016/06/16/when-were-statistics-updated-sqlnewblogger/> 
SELECT STATS_DATE ( <table/object_id>, stats_id) 

https://www.sqlpassion.at/archive/2021/01/07/sqlpassion-online-training-about-statistics-plan-caching/



## Types of Waits
## 1) Memory waits : 

there are 2 types here

#### 1.1 CMEMThread : 
----------------
	plan cache problem i.e. more plans are either added or removed from cache due to ad-hoc queries or non-parameterized workload. best fix is to  make app utilize parametrization.

	
#### 1.2 Resource_semaphore : 
-----------------------
	- occurs when requested memory is unable to obtain due to concurrent processes, large sort or hash operations. 
	if this waits are consistently occuring, check sys.dm_exec_queries_resource_semaphores to see how many waits are occuring.

	SELECT 
	waiter_count,
	timeout_error_count,
	forced_grant_count
	FROM sys.dm_exec_query_resource_semaphores

		/* values > 0 should be investigated further. */
        
        /* for further investigation, check below memory metrix from perfmon */

	 ➤ SQLServer:Memory Manager\Memory Grants Pending
	 ➤ SQLServer:Memory Manager\Memory Grants Outstanding
	 ➤ SQLServer:Buffer Manager\Buffer Hit Cache Ratio
	 ➤ SQLServer:Buffer Manager\Page Life Expectancy
	 ➤ SQLServer:Buffer Manager\Free Pages
	 ➤ SQLServer:Buffer Manager\Free List Stalls/sec
	 ➤ Memory: Available Mbytes

## 2.Disk I/O waits : 
----------------------
	waits occur when a process is waiting for disk I/O to complete before it can continue
	executing. The most common I/O waits in SQL Server are 
	
    	IO_COMPLETION, 
		ASYNC_IO_COMPLETION,
		WRITELOG, 
		PAGEIOLATCH_* waits.

	These wait types can be a sign that the disk subsystem is 
		- misconfigured, 
		- undersized, or 
		- overloaded for the current workload, 
				
	but they can also be a sign of other non-I/O-related problems, such as a 

    	- missing index, 
		- a query performing an expensive table
	    - scan being run without a WHERE predicate, or 
		- even memory pressure on the server.
		
Virtual file stats of all databases.
-----   
    SELECT 
	mf.name,
	mf.physical_name,
	vfs.IoStallMS,
	vfs.IoStallReadMS,
	 vfs.IoStallWriteMS, *
	FROM sys.fn_virtualfilestats(null,null) AS vfs JOIN sys.master_files AS mf ON mf.database_id = vfs.DbId AND mf.file_id = vfs.FileId ORDER BY vfs.IoStallMS DESC


** Disk : perfmon counters 

	 ➤ Average Disk sec/Read
	 ➤Average Disk sec/Write 
	 ➤ Average Disk Read/Write Queue Length

	 - Disks read or write times greater than 20 ms or high queue length values should be investigated  further, as these can be a sign of bottlenecking.
	
     - When looking at Disk IO bottlenecks, the memory counters listed in the Memory Waits section should also be examined.
	
    - also monitor how SQL Server accesses data. Table and index scans can be expensive compared to seeks. This can be a sign of a missing index or filter 
	criteria, requiring the database engine to read more data than would otherwise be necessary to satisfy the request. 
				   
    To monitor for this, collect the following performance counters:
	 ➤ SQL Server: Access Methods\Full Scans/sec
	 ➤ SQL Server: Access Methods \Index Searches/sec
	 ➤ SQL Server: Access Methods \Forwarded Records/sec

	 The Forwarded Records counter points to a specifi c problem with heaps that are frequently updated with variable-length data fields.


## 3.Blocking waits :

	- happens generally due  to concurrency locking. Long-term locking can be a sign of a possible transaction management issue inside of user code, but it can also be a sign of memory pressure on the server.

	- Looking at transaction duration with the sys.dm_tran_active_transactions DMV 
	
    - for the blocking session can help determine whether the problem is related to long-running user transactions.

    - In addition, enable the Blocked Process Report with sp_configure and then collect it using SQL Trace to capture detailed information about blocking.	


## 4.CPU waits :
	2 common CPU waits are
				
    - SOS_Scheduler_yields : 
				
        occurs when a task reached its quantum and yeilds to scheduler to other tasks in runnable list to allow them to execute. 
				
        When this wait type occurs along with a high signal wait to resource wait ratio, it can be a sign that more powerful processors are needed on the server.
				
    - CXpacket : 
		- happens when there is parallel processing with multiple tasks are used to satisfy a request in parallel. when data distribution is uneven, task with smaller data set will wait with this wait type to sync with other tasks.
				
        - Reducing the max degree of parallelism to a value that is less than the number of physical processors, or disabling parallelism completely using sp_configure, will resolve problems with this wait type.

## 5. Network Waits :
				
        Network waits (ASYNC_NETWORK_IO and DBMIRROR_SEND) occur when a session has to wait to transmit information over the network interface
				
				
        The ASYNC_NETWORK_IO :

		 - can be a sign that the current network adapter bandwidth is reaching a point of saturation. 
			
        - It can also be a sign that the client is not immediately consuming the results being returned by SQL Server.

		The DBMIRROR_SEND : 
		
        - can indicate that the available bandwidth is insufficient to support the volume of mirrored transactions occurring on the server. It can also indicate database mirroring oversubscription. 
				
		- If multiple databases are mirrored, try reducing the number of mirrored databases, or increasing the network bandwidth by upgrading to a higher-speed adapter.

	- To monitor network adapter performance, the following network performance counters
	can be collected:
	 ➤ Network\Current bandwidth
	 ➤ Network\bytes total/sec
	 ➤ Network\packets/sec

## 6.Pre-emptive waits

SQL Server usually uses co-operative scheduling, but when process makes external call like OLE automation, uses Extended Stored procs, the underlying tasks cannot be run co-operatively. instead, it uses pre-emptive scheduling in windows OS.

		SELECT * FROM sys.dm_os_wait_stats
		WHERE wait_type LIKE 'PREEMPTIVE%'
		order by waiting_tasks_count DESC



### Statistics & Plan Caching

• Statistics 

	○ Auto Create
	○ Auto Update
	○ Statistics Analysis
	○ Multi Column Statistics

• Cardinality Estimation 

	○ Conjunctions
	○ Disjunctions
	○ Ascending Key Column Problem

• Plan Caching 

	○ Adhoc Query Caching
	○ Parameterization
	○ Optimize for Adhoc Workloads

• Parameter Sniffing 

	○ Local Variables
	○ Recompilations
	○ Plan Guides
