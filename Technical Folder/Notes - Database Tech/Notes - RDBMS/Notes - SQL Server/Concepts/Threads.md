SQL server : THREADS

	What are threads?
	What are parallelism?
	Controlling parallelism?
	Thread scheduling?
	Components of scheduler.
	Schedulers in SQL server.
	Thread states
	The waiter list


What are threads?

	- Smallest unit of execution within process.
	- Multiple threads can exist within process.
	- Each thread is given certain amount of processor time to execute a process, beyond which it has to give up so that other threads can continue.
	- SQL Server uses operating system threads (worker threads).
	- Some of the threads are dedicated to specific tasks such as deadlock monitoring, checkpoint, etc
	- Most of the threads are in SQL pool from which SQL server picks up the threads when its necessary.


Pre-emptive scheduling : 
    
    sql server performs its own thread scheduling using SQLOS layer of storage engine.

Components of scheduler.

There are 3 components for all schedulers.

a. **Processor** : its actual processor where only 1 thread can run at a time.

b. **Waiter list** : list of threads waiting for resources.

c. **Runnable queue** : Queue of threads that have all resources and they are waiting for their turn.
	
Threads transition around these parts until task execution is completed.

	
One scheduler per physical or logical core. Plus some extra schedulers for internal and Dedicated admin connection.

There are 3 states of thread

a. **Running** : the thread is currently running on processor.

b. **Suspended** : the threads are currently doing nothing as its waiting for resources to be available.

c. **Runnable** : here threads are having all resources in the queue but are waiting for resources.
Threads transition around these parts until task execution is completed.

Special case : quantum exhaustion

- When thread execution cotinues and does not wait for any resource until it exhausts at its quantum. Here quantum is fixed at 4 ms. If this occurs then its state changes from RUNNING to RUNNABLE, skipping waiter-list.
 
What are parallelism?

- Sometimes query processor will use multiple threads execution in parallel  for efficient performance of user request, its known as parallelism.




**SQL Server Quickie #6 – THREADPOOL Starvation**:

 <https://www.sqlpassion.at/archive/2013/07/07/sql-server-quickie-6-threadpool-starvation/> 


