Locks in SQL Server database
********************

https://www.sqlshack.com/locking-sql-server/

https://www.youtube.com/watch?v=9lmPOTv-pDc

SQL Server Locks: 

https://www.sqlshack.com/locking-sql-server/
	
Understanding SQL Server Lock Escalation   :
https://logicalread.com/sql-server-2012-lock-escalation-mc03/#.YZ0zt2BBzIU
	
Understanding SQL Server Lock Granularity : 

https://logicalread.com/sql-server-lock-granularity-mc03/#.YZ0zuWBBzIU
	
Concurrency Models in SQL Server 2012       : 

https://logicalread.com/sql-server-concurrency-models-mc03/#.YZ0zbGBBzIU
	
Concurrency Control Models, ACID Properties and Transaction Isolation Levels : 

https://social.technet.microsoft.com/wiki/contents/articles/51484.sql-server-concurrency-control-models-acid-properties-and-transaction-isolation-levels.aspx
	
SQL Server Exploring Locks : 
    https://www.youtube.com/watch?v=wZRvVLwUb04
	
Lock Escalations                    :
    https://www.sqlpassion.at/archive/2014/02/25/lock-escalations/
    
Why do we need UPDATE Locks in SQL Server?: 
    <https://www.sqlpassion.at/archive/2014/07/28/why-do-we-need-update-locks-in-sql-server/> 



• Locks are designed to work seamlessly in multi-user environment & to ensure database integrity as it forces every transaction to pass ACID property test.


Levels of Locking's: is how rigidly lock is provisioned.
--------------------------------------------------------------------------

**Shared**: users cannot modify the data, but can view data.

**Exclusive**: other users should not be able to see the data that is about to be modified.

**Deadlock**: 2 processes are locking each other's resources that are required to execute.



## Types of locks:

**Exclusive Lock (X)**: 

    High priority lock will be acquired on the resource and will not allow any other locks on resource. Only 1 exclusive lock will be possible at any time.

**Shared lock (S)**:

	▪ It will reserve 1 data page, or 1 row for reading purpose. Several transactions acquire locks on same resources.

	▪ However write operations are allowed but not DDL statements.

**Update lock (U)**:

    ▪ Similar to shared lock but designed to be flexible in a way.

    ▪ An update lock (U) will be imposed on record that already has shared lock. In such case, update lock will impose another shared lock on the target row. Once the transaction is ready to make change of dta, then it will Impose Exclusive lock(X) on the target server.

    ▪ Update lock cannot be applied on the target row if it already has update lock.

**Intent lock (I)**:

			▪ This lock is used to inform other transaction about its intention to acquire lock. This is done to ensure proper data modification without any effect from other transactions trying to acquire lock in next hierarchy object.

			▪ Intent lock (I) happens on Table level. So other transactions cannot have row/page level access.
			▪ 
			There are 3 types of intent locks & 3 types of lock conversions.

			Intent exclusive (IX) : 
            
            This lock will tell SQL engine that it has intention of modifying some lower hierarchy resources by acquiring exclusive lock(X).

			Intent shared (IS)     : 
            
            This lock will tell SQL engine that it has intention of reading some lower hierarchy resources by acquiring shared lock(S).

			Intent update(IU)    : 
            
            The intent update (IU) can be acquired only at page level and acquires Intent Exclusive (IX) as soon as update operation takes place.

			Lock conversions:
				• Shared with intent exclusive (SIX):
				• Shared with intent update (SIU):
				• Update with intent exclusive (UIX):
	
	Schema locks (Sc): 
    
    sql engine recognizes 2 types of schema locks.

				• Schema modification (Sch-M):                 
                this type of lock is acquired for DML operations, it objects all other transactions on the table/object. Only 1 (Sch-M) possible at any time. 

					Ex: Rebuild Index tasks

				• Schema stability (Sch-U):                 
                this type of lock occurs when query executed & with execution plan generated. This does not prevent other transactions to acquire on objects but prevents the modifications of structures to tables/objects.
	
	Bulk update (BU):
				• This type of lock is applied when bulk import task is performed with TABLOCK hint. This will prevent other transactions to acquire locks. Other bulk operation cannot acquire (BU) lock at the same time parallelly.

Note: on clustered table, TABLOCK will not allow bulk import.
				
