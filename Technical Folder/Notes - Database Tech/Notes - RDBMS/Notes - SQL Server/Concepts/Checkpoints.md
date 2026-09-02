## Database Checkpoints (SQL Server)
https://docs.microsoft.com/en-us/sql/relational-databases/logs/database-checkpoints-sql-server?view=sql-server-ver15
		
• All the modified data pages will reside in memory (buffer cache) & will not be pushed to disk untill checkpoint occurs.

• Checkpoint is a Reference point from which all transactions can be applied in the log recovery process.

There are 4 types of Checkpoints

	• Automatic: checkpoint automatically applied in background with mentioned timeline as per Configuration settings.

	• Indirect: checkpoint issued background here as per user specified recovery time. Default is 1 in SQL 2016 version.
		 Command: ALTER DATABASE ... SET TARGET_RECOVERY_TIME =target_recovery_time { SECONDS | MINUTES }

	• Manual: manually checkpoint can be given using T-SQL command. 
    
	• Internal: internally checkpoints happens for various operations like Backups, db sapshots so that disk image of data matches that state in log.
	
	
