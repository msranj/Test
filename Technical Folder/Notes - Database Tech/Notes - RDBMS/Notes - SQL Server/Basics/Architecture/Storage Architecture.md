SQL Server Storage Architecture
    SQL Server stores data mainly in two types of files.
    
            1. Data File (MDF)
            2. Log File (LDF)

            
![alt text](image-1.png)

MDF  – It contains Permanent Data
LDF – LDF contains whatever changes we are performing on database all the change related information will be recorded in LDF file.

### SQL Server Buffer
	Buffer is a ram to perform modifications on a copy of permanent page. Once it commits record the information will record in LDF and same changes apply on MDF when checkpoint runs.

        How Buffer Works:
            SQL Server will not allow to do modifications directly on MDF. SQL Server will make a copy of pages from MDF to buffer. Once transaction is full committed it records the information that what type of data he is inserting, Number of pages affecting, what he is performing all these change related information will record in same sequential way in Log File. Pages will stay some time in buffer for faster retrieval read and write operations from buffer will be very faster comparing to operations from MDF Data. Using recorded information whenever check point runs on log file. It applies same changes permanently on MDF file.

### SQL Server Checkpoint Process
	Check point is internal mechanism performs regular based on number of transaction (or) number of pages there is no time interval for running this. Checkpoint scans log file, checks how many committed transaction are there, how many failed and how many still running committed transactions more to MDF, failed transactions will be rolled back. Currently running transactions will not to be touched by checkpoint.
	
	Advantages of checkpoint in SQL Server,
	Checkpoint help in speeding recovery process
	Checkpoint helping in committing data permanently
	
### SQL Server Recovery Process
	Whenever sql server restarts checkpoint verifies pending transactions before restart, sql server will perform recovery process. This process will analyze what is the state of log file and perform 2 properties.
	
	Redo (or) Roll forward –  committed changes will be moved from LDF to MDF permanently.
	Undo (or) Roll Back – failed transactions and running transactions will be deleted from log file.
	Once this recovery process complete then only users can able to access the database.

### Lazy Writer in SQL Server
	Modified pages will be in buffer for some time, whenever buffer is about to fill with these modified pages, Lazy writer is another internal mechanism usually in sleep mode invokes and clear the buffer pages.

	It uses LRU algorithm in clearing, LRU stands for L. Recently used pages, on page header of page there will e reference counter means how many times this page being used, based on counter least used pages will be deleted in buffer.

### Dirty Pages:
	Pages commit in log file and waiting for check point to more mdf, those called dirty pages.


**SQL Server Quickie #3 – Allocation Units** : <https://www.sqlpassion.at/archive/2012/09/18/sql-server-quickie-3-allocation-units/> 

**SQL Server Quickie #4 – IAM Pages:** <https://www.sqlpassion.at/archive/2012/10/16/sql-server-quickie-4-iam-pages/> 
