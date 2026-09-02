## MSDB Database

Mostly known as “the SQL Server Agent database” because it stores information of all 

		○ SQL Agent jobs & its configuration 
		○ Job execution history.
		○ Backups 
		○ Restores
		○ Service Broker 
		○ Database Mail 
	
MSDB has pre-defined database roles 

		○ Database mail
			▪ DatabaseMailUserRole

		○ Integration Services Roles
			▪ db_ssisadmin
			▪ db_ssisltduser
			▪ db_ssisoperator

		○ Data collector roles
			▪ dc_operator
			▪ dc_admin
			▪ dc_proxy

		○ Policy-Based Management
			▪ PolicyAdministratorRole

		○ Server Group
			▪ ServerGroupAdministratorRole
			▪ ServerGroupReaderRole

		○ SQL Server Agent Fixed Database Roles
			▪ SQLAgentUserRole
			▪ SQLAgentReaderRole
			▪ SQLAgentOperatorRole

		○ Multiserver Environment
			▪ TargetServersRole

		○ Server Utility
			▪ UtilityCMRReader
			▪ UtilityIMRWriter
			▪ UtilityIMRReader


## can MSDB be Detached?

msdb cannot be detached under normal conditions; if msdb is corrupted and there is no backup, start 
the instance in minimal configuration mode with trace flag 3608 (which skips auto-recovery of all 
databases except master) and then detach msdb manually. 


	net start MSSQLSERVER /T3608 /f /m"SQLCMD" 
	SQLCMD -E -S . -Q "EXEC sp_detach_db msdb"



