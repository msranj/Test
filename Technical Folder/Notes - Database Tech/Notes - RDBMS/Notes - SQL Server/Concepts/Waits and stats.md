SQL Server : Stats & Waits
-------------------------
Troubleshooting THREADPOOL Waits: https://www.sqlpassion.at/archive/2011/10/25/troubleshooting-threadpool-waits/

Inside the Statistics Histogram & Density Vector: <https://www.sqlpassion.at/archive/2014/01/28/inside-the-statistics-histogram-density-vector/> 

SQL Server Quickie #21 – Wait Statistics: <https://www.sqlpassion.at/archive/author/siteadmin/page/43/> 



SQL Server 2000 :
-----------------------
	- waits info was maintained under server level & info was retrieving from DBCC SQLPERF. currently waiting sessions could be viewed through the sysprocesses system view

SQL Server 2005 : 
-----------------------
	- stats info are retrieving using DMV by introducing the sys.dm_os_wait_stats 
    and 
    sys.dm_os_waiting_tasks.
	
	- Prior to SQL Server 2008, preemptive tasks either had no wait type associated with them or they had an obscure wait type like OLEDB associated with them, providing little information as to what the task was actually waiting for

SQL Server 2008 : 
-----------------------
	You can use the sys.dm_os_* view to look at the status of the various lists in the execution model.
    
    For example, you can find the 

		(sys.dm_os_schedulers) : number of schedulers (per logical core in each CPU).
		
        (sys.dm_os_workers) : workers assigned to the schedulers.
		
        (sys.dm_os_waiting_tasks) : currently waiting tasks assigned to the wait list. 
		
        (sys.dm_exec_ requests) : tasks in the runnable list waiting on CPU time.
        
        (sys.dm_os_wait_stats) : cumulative wait statistics for the entire instance. 



DMV to check on what is SQL Server waiting for
*******************************************
	There are 3 DMV for checking waits
		○ Sys.dm_os_waiting_tasks
		○ Sys.dm_os_wait_stats
		○ Sys.dm_exec_requests


sys.dm_os_wait_stats : 

this DMV is at server level with no detail level available. Also it is aggregated over time. 

	This table has following columns
		○ wait_type : type of waits thread encountered.
		○ waiting_tasks_count : count of each waiting task for thread associated since it started.
		○ wait_time_ms : total wait time for each wait task in milli seconds (inclusive of max_wait_time_ms)
		○ max_wait_time_ms : max wait time on wait type.
		○ signal_wait_time_ms : time difference between thread was signaled to get started and when it was started.


#### Note : 
------
you will need two snapshot of this dmv taken at some interval during issue. Second snapshot minus first snapshot will tell as where queries are waiting (If the slow performance is because of waits)

https://social.technet.microsoft.com/Forums/en-US/00f8f8a6-0fd5-4f31-9943-dfb48abad29b/sysdmoswaitstats?forum=sqldatabaseengine
	
		select * from sys.dm_os_wait_stats
		where max_wait_time_ms > 0
        order by wait_time_ms DESC

Because wait stats accumulate since the start of SQL server, it can be cleared manually using
	DBCC SQLPERF("sys.dm_os_wait_stats", clear). To check the current real time wait stats.


**clear the wait stats that accumulated since SQL Server restart**

		dbcc sqlperf("sys.dm_os_wait_stats",clear)


Script to check the actual wait stats in time difference of 5 secs.
	
	/*wait stats in time difference of 5 seconds*/

	IF OBJECT_ID('tempdb..#wait_stats') IS NOT NULL
	DROP TABLE #wait_stats
		SELECT *
		INTO #wait_stats
		FROM sys.dm_os_wait_stats
		WAITFOR DELAY '00:00:05'
	SELECT ws1.wait_type,
	 ws2.waiting_tasks_count - ws1.waiting_tasks_count
	AS waiting_tasks_count,
	 ws2.wait_time_ms - ws1.wait_time_ms AS wait_time_ms,
	 CASE WHEN ws2.max_wait_time_ms > ws1.max_wait_time_ms
	THEN ws2.max_wait_time_ms
	 ELSE ws1.max_wait_time_ms
	END AS max_wait_time_ms,
	 ws2.signal_wait_time_ms - ws1.signal_wait_time_ms
	AS signal_wait_time_ms,
	 (ws2.wait_time_ms - ws1.wait_time_ms) - (ws2.signal_wait_time_ms -
	 ws1.signal_wait_time_ms) AS resource_wait_time_ms
	FROM sys.dm_os_wait_stats AS ws2
	JOIN #wait_stats AS ws1 ON ws1.wait_type = ws2.wait_type
	WHERE ws2.wait_time_ms - ws1.wait_time_ms > 0
	ORDER BY ws2.wait_time_ms - ws1.wait_time_ms DESC
	
/*difference between resource and signal waits, it can be helpful to look at the percentage of total wait time that each contributes, as shown in the following example. 

A high percentage of signal waits can be a sign of CPU pressure or the need for faster CPUs on the server.
*/

	SELECT 
	SUM(signal_wait_time_ms) AS total_signal_wait_time_ms,
	SUM(wait_time_ms - signal_wait_time_ms) AS resource_wait_time_ms,
	SUM(signal_wait_time_ms) * 1.0 / SUM (wait_time_ms) * 100 AS signal_wait_percent,
	SUM(wait_time_ms - signal_wait_time_ms) * 1.0 / SUM (wait_time_ms) * 100AS resource_wait_percent
	FROM 
	sys.dm_os_wait_stats


To Check which specific tasks of queries are on waiting 
using sys.dm_os_waiting_tasks is preferrable with session > 50 as sesion id from 1-50 are for internal operation

sp_help [sys.dm_os_waiting_tasks]

    SELECT 
	 session_id,
	 exec_context_id,
	 wait_duration_ms,
	 wait_type,
	 resource_description,
	 blocking_session_id
    FROM sys.dm_os_waiting_tasks
    WHERE 
    session_id > 50
    ORDER BY session_id

/* 

No of tasks/queries waiting on each wait types. (snapshot in time, not historical)
higher no of tasks waiting for longtime can indicate
- increase workload,
- new query with poor performance
- some external process consuming high i/o

*/
    
    SELECT 
	wait_type,
	COUNT(*) AS num_waiting_tasks,
	SUM(wait_duration_ms) AS total_wait_time_ms
		FROM sys.dm_os_waiting_tasks
		WHERE session_id > 50
		GROUP BY wait_type
		ORDER BY wait_type


