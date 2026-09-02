References
- https://docs.microsoft.com/en-us/sql/odbc/reference/develop-app/transaction-isolation-levels?view=sql-server-ver15
- https://app.pluralsight.com/course-player?clipId=a38be2d7-d6d9-40b1-ae4f-8d99cd36abe8



Types of read
---------------------------
Transactions isolation levels are defined by below phenomena.

Dirty reads: 

    - Dirty Reads A dirty read occurs when a transaction reads data that has not yet been committed. 

Non-repeatable reads:

    - Don’t read the same row twice. Results are different.
	
Phantom Reads: 

    - Occurs when, during a transaction, new rows are added (or deleted) by another transaction to the records being read.

Dirty Reads: 

    - Data is modified in current transaction by another transaction. New rows can be added by other transactions, so you end up getting different number of rows by the same query in current transaction.



Transactions isolation levels
--------------------------------------------------------
	1. Read Uncommitted:
	2. Read committed:
	3. Repeatable Read: removes non-repeatable reads. Concurrency can be less. 
	4. Serializable: anomalies disappear.
	5. Snapshot : 

Myths and Misconceptions about Transaction Isolation Levels: <https://www.sqlpassion.at/archive/2014/01/21/myths-and-misconceptions-about-transaction-isolation-levels/> 

Interview question: 
----------------------
What two isolation levels in SQL Server will prevent phantom reads?
	- Serializable and Snapshot

