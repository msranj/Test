## Relational Engine:

Prepares the execution plan and submits to storage engine.

### Relational engine / Query Processing Architecture Guide

https://docs.microsoft.com/en-us/sql/relational-databases/query-processing-architecture-guide?view=sql-server-ver15

### Steps in executing a query
	
1. Server Network Interface (SNI) of the user establishes the connection between client and server using TCP/IP protocol, sends a query in TDS packets.
	
2. Query at command parser checks syntax errors then checks plan in plan cache of the buffer pool. If the plan not exists, pass the query to the optimizer.
	
3. The optimizer generates the best plan and passes it to the query executor, it reads the plan and passes it to the access method of the storage engine through OLEDB.
	
4. The access method requests the buffer manager to provide the data.
	
5. Buffer manager checks in the data cache of the buffer pool for an existing page. If the page not exists it pulls the 
required pages from the data (MDF) file, puts them in the data cache, and passes them to the access method.
	
6. Finally, the Access method passes the results back to the relational engine, from there it sent back to the user who executed the query.
