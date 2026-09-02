## SQL Server : Latches

- https://www.youtube.com/watch?v=NX5yCF5Myvs
					

Latches, Spinlocks & Lock-Free Data Structures Recording: https://www.sqlpassion.at/archive/2015/03/30/latches-spinlocks-lock-free-data-structures-recording/

Introduction to Latches in SQL Server: <https://www.sqlpassion.at/archive/2014/06/23/introduction-to-latches-in-sql-server/> 

Introduction to Spinlocks in SQL Server: <https://www.sqlpassion.at/archive/2014/06/30/introduction-to-spinlocks-in-sql-server-2/> 


## Latches
******
- Latches are internal to SQL engine and are used to provide memory consistency.
- Whereas locks are used by SQL Server to Maintain Logical Consistency.
- Latches are internal SQL server mechanism.
- Latches come in various modes

		- Destroy latch (DT)   : Most restrictive latch that occurs when the buffer content has to be removed from cache. It blocks all other latches.
		
        - Exclusive latch (EX) : Will acquired when data pages are being written. Prevents all other latches from acquiring.
		
        - Update latch (UP)   : Restriction similar to EX with exception that it allows read access to the pages.
		
        - Keep latch (KP)        : It is there to maintain the latch record order but also ensures that it stays until new latch being placed on it.
		
        - Shared latch (SH)    : Acquired when there is read access granted on page.



There are 3 types of Latches

	- I/O Latches : happens when data from Physical storages has to be loaded into Buffer pool.
	
    - Buffer latches : happens when data in Buffer pool are having contention due to high loads.
	
    - Non-buffer latches : happens on resources other than pages in buffer pool. Use LATCH_XX latch.
		Use cases:
			▪ Excess parallelism :
			▪ Too many Auto-Shrink / Auto-grow on databases
			▪ High Volume of DML loads on Databases


