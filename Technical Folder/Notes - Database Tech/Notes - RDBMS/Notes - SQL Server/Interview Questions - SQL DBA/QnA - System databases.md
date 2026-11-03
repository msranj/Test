
#### Questions on:  SYSTEM DATABASES


#### What is the significance of Model database?
	Ans: It is used as template for creating new databases. Any modifications to model will reflect the same in future created databases.
			
	Ex: suppose if DBA makes changes to Recovery model of Model Database to SIMPLE, then newly created databases will also 
	have SIMPLE Recovery model.
	
####  what is latch, different type of latches. use of latches
	Ans : Latch is internal Mechanism of SQL Engine.
	      3 types : I/O Latch, Buffer Latch, Non-Buffer Latch.
		 uses : to maintain consistency of Memory.
	
####  what are the reasons to get tempdb full.
	Ans : Heavy Log Transaction, Index Rebuild, Sorting operation etc
	
####  why tempdb files newly create after restart.
	
####  if sql service restarted, tempdb old files still exist or clear. if i create tempdb  .ndf file created that file exist or not after restarts.
	Ans : yes, files reside after restart.
	
####  what is the use of resource db, can we move the db from one place to another place. what could be the effect if move from one place to another.
	Ans : Yes, can be moved but not recommended by Microsoft as it may result in inconsistent Databases. But copy of the files can 
		be shared in another location. 
	
####  Resource db modified date is showing recent date, what are reasons.
	Ans: 

####  SQL Server Resource DB
		- Resource db is hidden database instance. we can see only mdf and ldf physically. It stores sql binaries files.
		- It provides high security to metadata, it contains all system objects such as system objects physically stores.
		- Resource db makes upgradation to new sql server version easier and faster. In earlier versions upgrading will delete and 
		create system objects. Now resource database will contain all system objects we take copy of resource database mdf and ldf
		and completes upgrading easily.
	


SQL Server: system databases
****************************
        https://www.sqlshack.com/sql-server-system-databases-the-master-database/
 
			§ Master
			§ MSDB
			§ Model
			§ Tempdb
			§ Resourcedb

Master:  
	####   Records all instance level information like logins, location of database log files & data files, accounts, 
	linked server, configuration, all users. 
	####  Changes in Master db happens when any updates/addition of logins, accounts, database file configurations, 
	patches on instances. so regular backup is recommended. 
 
	Moving master files to other loctions
	>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
		- go to SQL Server configuration manager
		- navigate to "startup parameters"
		- for master data file, navigate to data file 
			i.e. -d<new master file path>\master.mdf & press update (-d<without space, new file path>)
		- for master log file, navigate to data file 
			i.e. -l<new master file path>\master.ldf & press update (-l<without space, new file path>)
		- for master error log file, navigate to data file 
			i.e. -e<new master file path>\master.mdf & press update (-e<without space, new file path>)
		- for specific file, browse & update the path and save. when done press OK.
		- now, stop the SQL Services & physically change/update the master file to new location.
		- start the sql services. now master files will be in new location.
	 
		new: -dD:\Installation of Softwares\SQL Server - DB files\master.mdf
		old: -dD:\Installation of Softwares\SQL Server - Dev Edition\Microsoft SQL Server\MSSQL15.MSSQLSERVER\MSSQL\DATA\master.mdf
	 
	Restrictions on master databases
	>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
		- cannot rename master db
		- cannot change owner of master db
		- cannot drop master db
		- cannot take master db offline
		- cannot enable CDC on master db
		- cannot add more filegroups for master db or rename primary file group.
		- cannot delete guest user of master db
		- default collation of master db is without 
		- Triggers cannot be created on the master database system tables
		- A full-text catalog and full-text index cannot be created on the master database.
	 
 
	Restore master Database
	------------------------
			Warning: In the event of disaster recovery, the instance where the master database is being restored to should be as close to 
			an exact match to the original as possible. 
			At a minimum, this recovery instance should be the same 
				> version, 
				> edition, and 
				> patch level, and it should have the 
				> same selection of features and the same external configuration (hostname, cluster membership, and so on) as the 
				original instance. 
			Doing otherwise might result in undefined SQL Server instance behavior, with inconsistent feature support, and 
			is not guaranteed to be viable.
			 
	To Restore the Master database
	-------------------------------------
			1) Start the server instance in single-user mode.
			2) To restore a full database backup of master, use the following RESTORE DATABASE Transact-SQL statement:
			>> RESTORE DATABASE master FROM <backup_device> WITH REPLACE
			Note: 
				After master is restored, the instance of SQL Server shuts down and terminates sqlcmd process. Before you restart 
				the server instance, remove the single-user startup parameter.
			3) Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, 
			and correcting user mismatches.
		 
	Rebuild Master/MSDB/Model/System db in case of
			> corruption in master/system dbs
			> modify the server level collation.
			 note: after rebuild on existing master/msdb/model db & its associated packages/jobs etc will be lost.
		 
	Pre-requisties: steps before Rebuild of systemdatabases
	https://docs.microsoft.com/en-us/sql/relational-databases/databases/rebuild-system-databases?view=sql-server-ver15
		    1) make a note of all configurations, packages/pacthes applied on instances
			2) copy the template files of all master, msdb, model db as its required during the rebuild process. 
			if not, use repair feature of setup & manually copy to SQL Server template directory.
			3) if replciation is configured, take backups of distributor db
			4) backup master, msdb, model dbs
			5) make a note of all data/log file locations of all master, model,msdb as the location of these files will be in 
			default location after rebuild.
	 
Rebuild process:
>>>>>>>>>>>>>>>>
		on stand alone server, its normal procedure.
		on clustered instances, perform the activities on active node, its resources must be taken offline first.
	
To rebuild system databases for an instance of SQL Server:
----------------------------------------------------------
		1) Insert the SQL Server installation media into the disk drive, or, from a command prompt, change directories to the 
		location of the setup.exe file on the local server. 
		The default location on the server is C:\Program Files\Microsoft SQL Server\130\Setup Bootstrap\SQLServer2016.
		 
		2) From a command prompt window, enter the following command. Square brackets are used to indicate optional parameters. 
		Do not enter the brackets. 
			cmd>> Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName /SQLSYSADMINACCOUNTS=accounts [ /SAPWD= StrongPassword ] [ /SQLCOLLATION=CollationName]
		 
		3) When Setup has completed rebuilding the system databases, it returns to the command prompt with no messages. 
		Examine the Summary.txt log file to verify that the process completed successfully. 
				This file is located at C:\Program Files\Microsoft SQL Server\130\Setup Bootstrap\Logs.
		 
Post-Rebuild Tasks
		After rebuilding the database you may need to perform the following additional tasks:
			1) Restore your most recent full backups of the master, model, and msdb databases. 
			2) If the instance of SQL Server is configured as a replication Distributor, you must restore the distribution database.
			3) if location change required for system dbs, Move the system databases to the locations you recorded previously.
			 
Rebuild the resource Database
------------------------------
	The following procedure rebuilds the resource system database. When you rebuild the resource database, all hot fixes are lost, 
	and therefore must be reapplied.
	
	To rebuild the resource system database:
	>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
			1) Launch the SQL Server Setup program (setup.exe) from the distribution media.
			2) In left navigation area, click Maintenance, and then click Repair.
			3) Setup support rule and file routines run to ensure that your system has prerequisites installed and that the 
			computer passes Setup validation rules. 
			Click OK or Install to continue.
			4) On the Select Instance page, select the instance to repair, and then click Next.
			5) The repair rules will run to validate the operation. To continue, click Next.
			6) From the Ready to Repair page, click Repair. The Complete page indicates that the operation is finished.
	 
Create a New msdb Database
----------------------------
If the msdb database is damaged and you do not have a backup of the msdb database, you can create a new msdb by using the instmsdb script.
by rebuilding msdb, all jobs, packages, reports, alerts, notifictaions will be lost.
	 
	1)Stop all services connecting to the Database Engine, including SQL Server Agent, SSRS, SSIS, and all applications using SQL Server 
	as data store.
    
	2)Start SQL Server from the command line using the command: NET START MSSQLSERVER /T3608

	3) In another command line window, detach the msdb database by executing the following command, replacing <servername> with 
	the instance of SQL Server: 
		CMD>> SQLCMD -E -S<servername> -dmaster -Q"EXEC sp_detach_db msdb"
	4) Using the Windows Explorer, rename the msdb database files. By default these are in the DATA sub-folder for the SQL Server instance.

	5) Using SQL Server Configuration Manager, stop and restart the Database Engine service normally.

	6) In a command line window, connect to SQL Server and execute the 
		cmd: SQLCMD -E -S<servername> -i"C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\Install\instmsdb.sql" 
		-o"C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\Install\instmsdb.out"
	Replace <servername> with the instance of the Database Engine. Use the file system path of the instance of SQL Server.
	7) Using the Windows Notepad, open the instmsdb.out file and check the output for any errors.
	8) Re-apply any hotfix installed on the instance.
	9) Recreate the user content stored in the msdb database, such as jobs, alert, etc.
	10) Backup the msdb database.

 ####  Tempdb

# Rebuild the tempdb Database
------------------------------
If the tempdb database is damaged and the database engine fails to start, you can rebuild tempdb without the need to rebuild all system databases.   
	1) Rename the current tempdb.mdf and templog.ldf files, if not missing.  
	2) Start SQL Server from a Command Prompt by using the following command.  

			cmd>> sqlservr -c -f -T3608 -T4022 -s <instance> -mSQLCMD (for named instance use MSSQL$<instance_name>)

	Note : 
    
    Make sure that the command prompt window remains open after the SQL Server starts. Closing the command prompt window will 
	terminate the process.  

3) Connect to the server by using sqlcmd, and then use the following stored procedure to reset the status of the tempdb database.
			sqlcmd> exec master..sp_resetstatus tempdb

4) Shut down the server by pressing CTRL+C in the command prompt window

5) Restart the SQL Server service. This creates a new set of tempdb database files, and recovers the tempdb database. 
	
#### TempDB file movement.#### 
	####  Take backup of all databases.
	####  Take output of Tempdb database.
			Use Tempdb
			go
			sp_helpfile
			go
	####  Execute the below script to move tempdb files from E drive to T drive
			USE master;
			GO
			ALTER DATABASE tempdb
			MODIFY FILE (NAME = tempdev, FILENAME = ‘T:\Datafiles\tempdb.mdf’);
			GO
			ALTER DATABASE tempdb
			MODIFY FILE (NAME = templog, FILENAME = ‘T:\Datafiles\templog.ldf’);
			GO
	####  Restart SQL Server.
Check the database consistency.
 
#### Roll Back plan: TempDB file movement.

	Execute the below script to move tempdb from T drive to E drive
		 
	USE master;
	GO
	ALTER DATABASE tempdb
	MODIFY FILE (NAME = tempdev, FILENAME = ‘E:\Datafiles\tempdb.mdf’);
	GO
	 
	ALTER DATABASE tempdb
	MODIFY FILE (NAME = templog, FILENAME = ‘E:\Datafiles\templog.ldf’);
		GO
	
    Restart SQL Server.
	
    Check the database consistency.
 
####  Tempdb full: how to troubleshoot 

https://anchalmalwal.wordpress.com/2015/09/13/how-to-troubleshoot-if-tempdb-full/


	- check DBCC sqlperf(logspace) -- how much log space is used. 
	
    - select name,log_reuse_wait_desc from sys.databases --- for what reason log file is waiting
	
    - Check active transactions
	- Check open transactions through: DBCC OPENTRAN
	- Run below three commands after approval. Because there is a risk involved with this, it‘s mention below with commands.
			DBCC FREESYSTEMCACHE(‘ALL’)
			DBCC FREESYSTEMCACHE (‘tempdb’)
			DBCC FREESYSTEMCACHE (‘Temporary Tables & Table Variables’)
    - add another log file to tempdb if required.
	- The last Option is restart the instance after Approval.
		
		
		
						