### Concurrency Models
*********************
https://app.pluralsight.com/course-player?courseId=0f03fd19-980d-425f-9a80-679988f15d70 - Gerald Britton

		
https://blog.sqlauthority.com/2012/11/15/sql-server-concurrency-basics-guest-post-by-vinod-kumar/

https://logicalread.com/sql-server-concurrency-models-mc03/#.YZ4rqqJBzIV



Topics:

	Ø SQL Server Concurrency control
	Ø Understanding transactions
	Ø Managing basic isolation level
	Ø Implementing snapshot isolation levels
	Ø Locking in database engine
    Ø Optimizing concurrency & Locking behavior



What is Concurrency?

Multiple processes running execution at same time.
	
    Multitasking Model
				Ø Pre-emptive: interruptible
				Ø Cooperative: yield control of CPU
		
Concurrent operations have impact on database integrity. For database to have integrity a RDBMS should must comply ACID Principle which is normally implemented through transactions.
	
	A : Atomicity
	C : Consistency
	I : Isolation
    D : Durability

Atomicity:

	When data is modified by some transactions, either 
	ALL of transactions should happen 
	OR 
	NONE of the transactions should happen.
		
Consistency:

	When data is modified by some transactions. All the 
			§ Data must be consistent state
			§ All Constraints must be satisfied
			§ All internal structures must be correct.

Isolation:

    Modifications made by each transactions must be isolated from other concurrent transactions.
	
Durability:

	When transactions is complete, it must be stored in system to restore in later cases if required.
			
### SQL Server supports 2 types of concurrency models

	• PESSIMISTIC concurrency
	• OPTIMISTIC concurrency


Pessimistic concurrency:  

	• works on assumption that conflicts in database transactions are unavoidable. So it blocks the rows needed to modify the data by 2 or more transactions by applying locks on the target resources.

	• No other process can read the data that is being modified as it is locked.

Optimistic concurrency:

	• works with assumption that a transaction is unlikely to make data modification when another transaction is already performing same data modification.

	• Here old version of data will be saved for other read transactions using row versioning.


DELETE operations on tables: <https://www.sqlpassion.at/archive/2014/02/11/delete-operations-on-tables/> 



