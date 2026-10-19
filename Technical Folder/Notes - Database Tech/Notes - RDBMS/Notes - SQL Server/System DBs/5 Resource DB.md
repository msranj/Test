
## Resource DB

https://www.vembu.com/blog/resource-database-sql-server/

		○ Resource db maintains sys objects of SQL server. Here sys objects maintain the metadata and the data of tables, views, stored procedures of system tables and DMV.

		○ Objects in resource DB is available through logical links in sys schema of all databases.

		○ Any hidden objects in system objects can be viewed with sa rights.

		○ The location of resource database is as shown below. Should not be changed as it leads to inconsistency.
		
			C:\Program Files\Microsoft SQLServer\Instance_Name\MSSQL\Binn\mssqlsystemresource.mdf
			C:\Program Files\Microsoft SQL Server\Instance_Name\MSSQL\Binn\mssqlsystemresource.ldf
		
		○ Using DAC, the Resource DB files can be accessed.
		○ Cannot attach the resource DB as it’s a normal binary file.

KB Article : Resource DB Files missing post install of service packs for multiple instances after reboot.

	https://support.microsoft.com/en-us/topic/kb3074535-fix-the-resource-database-is-missing-after-you-install-updates-or-service-packs-for-instances-of-sql-server-2012-one-after-another-and-then-restart-the-server-194c1a0d-0a15-5324-1886-5fc82fe4ef6f

Find the location of the Resource Database By running the below T-SQL script, you can find the location of the Resource Database of your SQL Server instance(s).
		
		USE master;
		GO
		
		SELECT 'ResourceDB' AS DBName ,
		       [name] AS DBFile,
		       [filename] AS FilePath
		FROM   sys.sysaltfiles
		WHERE  dbid = 32767;
		GO
