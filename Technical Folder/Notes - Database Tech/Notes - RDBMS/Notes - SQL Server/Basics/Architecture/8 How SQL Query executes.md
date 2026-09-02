## How SQL Server executes a Query: 

	- https://www.sqlpassion.at/archive/2022/01/25/how-sql-server-executes-a-query/
    - Life Cycle of a Query in SQL Server with Deepthi Goguri : https://www.youtube.com/watch?v=eG0iKV75G4U

The following pictures give you an overview about the most important components within SQL Server, that are used when we are executing a query.

 SQL Server is internally split up into the below

	- Relational Engine, 
	- Query Optimizer and  
	- Storage Engine
	


[SQL Query Exec steps] (https://www.sqlpassion.at/wp-content/uploads/2022/01/SQLServerComponents.png)


The biggest component within the relational engine is the Query Optimizer.

### ** Reading data**

The query – that we are submitting to SQL Server – goes through the **Protocol Layer** to the **Command Parser**. The command parser just checks if we are providing a valid TSQL statement, if we are referencing tables and columns that exist in our database. The result of the command parser is a so-called **Query Tree**, a tree structure that represents our query. The tree structure is used by the query optimizer to generate an execution plan.
	
The compiled execution plan is afterwards handed over to the Query Executor. The task of the query executor is to execute the execution plan. But in the first step the compiled plan is cached in the Plan Cache for further reuse. Plan Caching is a powerful and at the same time also a very dangerous concept in SQL Server. We will also cover that important topic throughout the next weeks.
	
After our execution plan is cached, the query executor communicates with the storage engine, and executes every operator in our execution plan. When we are accessing data in our execution plan (we are always doing that!), the **Access Methods** are asking the **Buffer Manager** for specific pages that we want to read. 
	
The buffer manager manages the **Buffer Pool**, where our pages of 8kb are stored. The buffer pool itself is the main memory consumer of SQL Server and its size can be configured through the Min/Max Server Memory Setting.
	
When a requested page is already stored in the buffer pool, the page is immediately returned. This is a so-called **Logical Read** in SQL Server. If the page is not stored in the buffer pool, the buffer manager issues an asynchronous I/O operation to read the requested page physically from our storage subsystem into the buffer pool. This is a so-called **Physical Read**. During the asynchronous I/O our query has to wait until the operation is completed.
	
As soon as the page is read into the buffer pool, the page is returned back to the access method that requested it. When the execution plan is finished, the produced data is returned through the protocol layer back to the application that submitted the query.

**Changing data**
	
When we are dealing with TSQL statements that are changing data (INSERT, UPDATE, DELETE, MERGE), the storage engine also interacts with the **Transaction Manager**. The transaction manager writes transaction log records into the transaction log that describe the changes we have performed for the transaction. As soon as these records are written out, the transaction can commit. This also means that your SQL Server instance can be only as fast as your transaction log.
	
Pages that were changed in memory are written to the storage subsystem through the so-called CHECKPOINT process. By default, the CHECKPOINT process runs about every minute, and requests all dirty pages from the buffer manager. A dirty page is page that was changed in memory but hasn’t yet been written to the storage. As soon as a dirty page is written out to the storage, the page is marked as a clean page.

