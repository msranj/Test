## Memory component / buffer pool

References:
*********

- https://www.ourtechideas.com/sql-server-architecture/
- Inside the Memory of SQL By Bob Ward - https://www.youtube.com/watch?v=cCfwSsagDUk


**Memory Management Architecture / Buffer pool Guide**

	https://docs.microsoft.com/en-us/sql/relational-databases/memory-management-architecture-guide?view=sql-server-ver15

**Memory Management / Buffer Pool**:

Contains plan cache & data cache that is used for query execution.
	
The buffer pool is another important component that contains
		○ Plan cache and 
		○ Data cache 
	which is used for query execution.

**Query Memory/Workspace Memory**:

Query memory (also known as workspace memory) is used to temporarily store 	results during hash and sort operations when executing a query
	
	- sys.dm_exec_query_memory_grants 


**Query Wait**: 
	
Queries can timeout if they spend too much time waiting for a memory grant. The timeout duration is controlled by the Query Wait option, which can be modified using sp_configure or on the Advanced page of Server Properties in Management Studio.
	
    Query Memory : Perfmon counters** 

    Granted Workspace Memory (KB)**: Total amount of query memory currently in use.

    Maximum Workspace Memory (KB)**: Total amount of memory that SQL Server has marked for query memory
        
    Memory Grants Pending**: Number of memory grants waiting in the queue

    Memory Grants Outstanding**: Number of memory grants currently in use
	
The **RESOURCE_SEMAPHORE** wait type is a wait on a memory grant, so if you see this near the top in your results from the sys.dm_os_wait_stats DMV then your system is struggling to provide memory grants fast enough.
	
you may notice Hash Warning or Sort Warning messages if you have selected the relevant events. These occur when the memory grant was insufficient for a query’s requirements


