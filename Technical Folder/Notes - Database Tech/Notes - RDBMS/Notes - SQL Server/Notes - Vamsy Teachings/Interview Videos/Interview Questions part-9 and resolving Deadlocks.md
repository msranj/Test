# Interview Questions part-9 and resolving Deadlocks 

Reference:
- https://youtu.be/Eq1jdw40duk

- https://learn.microsoft.com/en-us/troubleshoot/sql/database-engine/performance/troubleshoot-slow-running-queries



Video timelines
------------------
0:00 - 12:11 // demo of deadlocks

12:12 - 32:45 // how to index to avoid deadlocks

32:49 - //  how to create a right index & avoiding the blockings also.

#### 12:12 - 32:45 // how to avoid deadlocks
------------------------------------------------------------
- Use NOLOCK
- Check the indexes on tables.
- Using a demo script, we analysed & created an index with lead column from predicate & other columns in output list into included columns.
- Once an index with above criteria is created we avoided deadlocks, but blockings were there.


#### 32:49 - 51:30 //  how to create a right index & avoid the blockings also.

#### 51:30 - //  how will you categorize the CPU bound Query & IO bound query?

https://learn.microsoft.com/en-us/troubleshoot/sql/database-engine/performance/troubleshoot-slow-running-queries

For the past executed queries, use below query & replace <your query > with required text

```SELECT t.text,
     (qs.total_elapsed_time/1000) / qs.execution_count AS avg_elapsed_time,
     (qs.total_worker_time/1000) / qs.execution_count AS avg_cpu_time,
     ((qs.total_elapsed_time/1000) / qs.execution_count ) - ((qs.total_worker_time/1000) / qs.execution_count) AS avg_wait_time,
     qs.total_logical_reads / qs.execution_count AS avg_logical_reads,
     qs.total_logical_writes / qs.execution_count AS avg_writes,
     (qs.total_elapsed_time/1000) AS cumulative_elapsed_time_all_executions
FROM sys.dm_exec_query_stats qs
     CROSS apply sys.Dm_exec_sql_text (sql_handle) t
WHERE t.text like '<Your Query>%'
```

-- Replace <Your Query> with your query or the beginning part of your query. The special chars like '[','_','%','^' in the query should be escaped.
ORDER BY (qs.total_elapsed_time / qs.execution_count) DESC

- Below screenshot shows Avg_CPU_time = 0 (so its NOT CPU bound, but IO Bound query)









