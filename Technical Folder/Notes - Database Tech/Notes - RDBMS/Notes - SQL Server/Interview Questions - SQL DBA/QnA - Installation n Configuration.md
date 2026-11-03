Questions on : Installation & configurations
**********************************************************


http://udayarumilli.com/installing-sql-server/
  
#### What’s the practical approach of installing Service Pack?####
Steps to install Service pack in Production environments:
		 

1) Get the necessary approvals for the downtime window. Normally it takes around 45-60 minutes to install Service pack if there are no issues.
		
2) Once the downtime window is started, take a full backup of the user databases and system databases including the Resource database.

3) List down all the Startup parameters, Memory Usage, CPU Usage etc and save it in a separate file.

4) Install the service pack on SQL Servers.

5) Verify all the SQL Services are up and running as expected.

6) Validate the application functionality.
		
Note: 

There is a different approach to install Service pack on SQL Server cluster instances. That will be covered in SQL Server cluster.
  
#### #### Q>what is a slip stream installation and its usages?#### 

	https://www.dbamantra.com/sql-server-dba-interview-questions-and-answers-installation/

Ans: SQL Server 2008 introduced a concept that’s called “Slipstream Installation”. This is a way to deploy a SQL Server instance with all the 
needed Service pack as part of the installation. Everything will be installed in one go, hence there is no need to deploy any other service 
packs on the installation.
	 
#### #### Q>What is a silent installation and how can we use this feature?####

Ans: The procedure to install SQL Server instance through command line using ConfigurationFile.ini file in Quite mode is known as Silent installation.
 
#### #### Q>What are Shared Features Directory and its usages? ####

Ans: This directory contains the common files used by all instances on a single server 

		e.g. SSMS, 
			 sqlcmd, 
			 bcp, 
			 DTExec etc. 
These are installed in the folder <drive>:\Program Files\Microsoft SQL Server\110\ , 

where <drive> is the drive letter where components are installed. The default is usually drive C.
 
#### #### Q>What are the file locations for Server components?####

Ans: Server components are installed in directories with the format <instanceID>\<component name>. For example, a default or named instance with the Database Engine, Analysis Services, and Reporting Services would have the following default directories:
	 
    <Program Files>\Microsoft SQL Server\MSSQL.1\MSSQL\ Database Engine

    <Program Files>\Microsoft SQL Server\MSSQL.2\OLAP\ for Analysis Services

    <Program Files>\Microsoft SQL Server\MSSQL.3\RS\ for Reporting Services
		 
#### #### Q>What are the prerequisites for installing SQL Server 2008?
		Ans: Microsoft SQL Server 2008 setup requires Windows Installer 4.5 and .Net Framework 3.5 SP1 to be installed.
 
#### #### Q>What permissions are required for a user install SQL Server on a server?
		Ans: Local administrator permission.
 
#### Q>I already have SQL Server 2008 instance and now I want to update to service pack 1. Do I need to use slipstream?
		Ans: No, slipstream will not work when the product is already installed.
 
#### Q>I am hitting the error: “The setting ‘PCUSOURCE’ specified is not recognized.”

Ans: If you have followed the slipstream instructions, ensure the path to PCUSOURCE does not contain spaces. 

The setup does not handle the spaces as expected.  The quick workaround is to rename the PCUSource path so it does not contain any spaces. You can confirm this is the problem by viewing the 

    Detail_ComponentUpdate.log located at %programfiles%\Microsoft SQL Server\100\Setup Bootstrap\Log\<last session>. 

Search for “PCUSource”. If you see commas in the PCUSource path, this is the issue:
 
#### Q>Can I slipstream in any CU?

Ans: In general, yes.  However, you need to ensure the CU will work the original release (RTM) or SP.  

    For example, 
    
    if you are slipstreaming Service Package 1 (SP1), then only CUs based on SP1 can be slipstreamed into the installation. 
    
    If you are not slipstreaming a service pack, then you need to ensure the CU is for the original release.

 #### Q>Can I use slipstream to upgrade from SQL 2005 to SQL Server 2008?
		Answer: Yes.
#### Q>Can I use slipstream to upgrade from SQL 2000 to SQL Server 2008?
		Answer: Yes.
#### Q> Is there a way to find out when a patch / sp was last applied to an instance?

Ans: 
			
    Start SSMS, 
    open help menu and 
    go to “about”

		Run Select @@version
	
    	Run SELECT SERVERPROPERTY(‘productversion’), SERVERPROPERTY (‘productlevel’), SERVERPROPERTY (‘edition’)
	
    		Run XP_READERRORLOG and from the result set we can find the version details
	
    If nothing worked as far as I know only option there would be to look at the add/remove programs list (or dump this data from the registry to make it easier to deal with) and get that info from there. SQL Server doesn’t track that within the system databases.
 
#### Q>What is the default port number in SQL Server Instance?
		Ans: 1433.
 
#### Q>What is SQL Server Browser Services Port number.
		Ans: 1434.
 
#### Q>What is FILE STREAM?

Ans: FILE STREAM was introduced in SQL Server 2008 for the storage and management of unstructured data. The FILESTREAM feature allows 
storing BLOB data(word document, image file, music etc).
 
#### Q>How many default SQL Server error log files are generated? 

Ans: By default 7 (seven) SQL Server error log files was generated. ERRORLOG and ERRORLOG.1 through ERRORLOG.6

 #### Q>What is a service account?
Ans: Mainly we categorize the Service account as below:

Local User Account: 

	This user account is created in the server where SQL Server is installed; 

	this account does not have access to network resources.

				 
Local Service Account: 

	This is a builtin windows account that is available for configuring services in windows. 

    This account has permissions as same as accounts that are in the users group, 
	thus it has limited access to the resources in the server.
				 
Local System Account: 

	This is a builtin windows account that is available for configuring services in windows. 

	This is a highly privileged account that has access to all resources in the server with administrator rights.
				 
Network Service Account: 

	This is a builtin windows account that is available for configuring services in windows. 

	This has permissions to access resources in the network under the computer account.
				 
Domain Account: 

	This account is a part of our domain that has access to network resources for which it is intended to have permission. 

	It is always advised to run SQL Server and related services under a domain account with minimum privilege need to run SQL Server and its related services.
				
	
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
				
	
