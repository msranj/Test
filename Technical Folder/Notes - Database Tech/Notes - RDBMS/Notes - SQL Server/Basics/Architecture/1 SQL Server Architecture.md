
# Server - DB Architecture 

    https://www.youtube.com/watch?v=jskazgQ9_VI 

    https://www.ourtechideas.com/sql-server-architecture/ 
    
    https://kindsonthegenius.com/mssql/ms-sql-server-architecture/ 

    https://support.quest.com/de-de/technical-documents/spotlight-on-sql-server/10.0.3/getting-started-guide/a-review-of-the-sql-server-architecture


The 3 components of the SQL Server architecture would be covered: 
- **Protocol Layer**
- **Relational Engine**
- **Storage Engine**


SQL Server Architecture
-------------------------------
![SQL Server Architecture](https://tse3.mm.bing.net/th/id/OIP.24lcGg_y8PdRSaQK8Jl1QgAAAA?cb=defcachec2&rs=1&pid=ImgDetMain&o=7&rm=3) 

![SQL Server Architecture2] (https://support.quest.com/de-de/technical-documents/image/38e491fa-e5a8-44bf-9854-8827d0d5bdd5)

### **1. The Protocol Layer**

This Layer specified the communication between the client and the database server. MS SQL server support three types of client-server protocols 

    Shared Memory: 
    client & host in same local machine.

    Named Pipes: 
    client & host in same Local network. 

    TCP/IP: 
    client & host in remote connections 

These can be seen in the SQL Server configuration manager windows shown below: 

![SQL Server configuration manager](https://www.ifixproblem.com/wp-content/uploads/2021/08/sql-server-configuration-manager-816x618.png)

### **2. Relational Database Engine** 

This is also known as the Query Processor engine.  
- Determines what operations would be executed by a query.  

- Handles how to improve performance of the query. When necessary, it request data from the data storage engine, processes and sends back the result to the client. 

There are 3 sub-components here: 

    CMD Parser : 

    This is the first component that receives the query. It checks if query is correct ( in syntax and semantics). It then generates the syntax tree. 

    Query Optimizer: 

    This creates and execution plan for the query. The execution plan specifies how the query would be executed. 

    Query Executor : 

    This actually executes the query by first calling the Access Method and providing an execution plan for fetching data. 


### **3. Storage Engine**

This is core storage area of the architecture. The types of files stored by the storage engine includes transaction log files (.ldf ) and data files(mdf).  

These are explained below: 

    Data Files (.mdf) : 

    This is also called the Primary File.This is the file that stores the database objects: tables, views, stored procedures etc.  It normally has the extension .mdf. 

    Transaction Log Files(.ldf): 

    These files are used for transaction management. They help to recover the database in case of failure. Transaction logs are also called  write-ahead logs. 

    Secondary Files (.ndf): 

    This is an optional file that holds user-specific data. They normally have the extension .ndf. Let’s now talk about two more components: Transaction Manager and Buffer Manager 

    Transaction Manager:

    Manages  non-select transaction with the help of log manager and lock manager. Once the access method determines that the query is non-     select, the Transaction Manager is invoked. 

    Buffer Manager:

    Manages functions such as: Plan Cache, Data Parsing and Dirty Page. 

    Lazywriter: 
    An internal process that works to free all types of cache. 

