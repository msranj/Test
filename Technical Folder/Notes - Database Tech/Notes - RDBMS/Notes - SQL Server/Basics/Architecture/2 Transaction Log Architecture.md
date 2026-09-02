## Transaction Log Architecture  

- https://docs.microsoft.com/en-us/sql/relational-databases/sql-server-transaction-log-architecture-and-management-guide?view=sql-server-ver15 

Andrey Langovoy blogs on Transactional logs

- https://codingsight.com/dive-into-sql-server-transaction-log-part-1/

- https://codingsight.com/dive-into-sql-server-transaction-log-part-3/


#### SQL Server Transaction Log Architecture

![TLog file with VLF and Log Blocks](https://codingsight.com/wp-content/uploads/2021/10/image-3.png)

SQL Server uses **LSN (Log Sequential Number)** in identifying the transaction. Each and every transactions that comes to log file will associate with a LSN number. Roll forward and roll back will be done internally using these LSN numbers only. 

**<u>WAL (Write Ahead Logging)</u>**: 

Before commit in MDF, every transaction should have written entry in log file is called WAL. Transactions never comes to mdf directly. 
 
Log file divided into 2 parts. 

**1. Active portion (or) Physical Log** 

**2. Inactive Portion (or) Virtual Log**

**Active Log Portion**: whenever transactions performs it will have 3 states. 

    1. Committed in log file and waiting for check point. 
    2. Failed in the middle 
    3. Transactions still running 

    All these 3 states transactions will be in Active Portion of Log file. When checkpoint runs committed transactions make a copy in inactive portion and moves to mdf. 

**Inactive Log Portion**: 

    SQL Server maintains fully committed transaction in these Inactive portion. 
    This portion only used for taking the backup of log. Whenever we take log backup it copies the inactive portion and truncates the inactive portions. 

    Full backup takes backup of MDF and Active log portion log backup takes backup of inactive log portion. 
    This portion we call as virtual log. SQL Server not uses these records that’s why it call as Inactive virtual logs. 

    Inactive portion further divided into more virtual logs we have a property called log reusability. 
    Log backup copy inactive portion to a file and truncates the log data. 
    Same space can be used multiple times called log reusability concept. 

    Transaction log is a cyclic process of writing log record into virtual log file by sql server. Whenever one virtual log is filled up it will goes to next virtual log. 
    If all virtual logs files are filled up the inactive portion will grow further and creates more virtual logs, till we have log space allocated. 
    If it cannot grow further it will throw an error “ Transaction log for database is full and transaction will fail”. 

    The only way to clear inactive virtual log is to take log backup released logs. 
    After truncation this space will be released. Backup will not active portion. 

    Advantages of T-Log: 

    - IT provides Transactional consistency. 
    - It provides transactional recoverability 
    - It provides log reusability. 

 

















