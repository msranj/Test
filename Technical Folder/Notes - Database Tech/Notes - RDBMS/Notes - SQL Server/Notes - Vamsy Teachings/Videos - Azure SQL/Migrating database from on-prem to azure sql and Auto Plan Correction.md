# Migrating database from on-prem to azure sql and Automatic Plan Correction
Reference: https://learn.microsoft.com/en-us/data-migration/sql-server/database/guide


Pre-requisties
-----------------
Different stage involved in Migration process flow
1. Discover
2. Assess
3. Migrate
4. Cutover
5. Optimize
  
 Discover:
 - what servers are in inventory.
	-- Azure migrate
	-- Microsoft assessment and planning toolkit 
    (MAP toolkit)
	
Assess:
- check for any issues with migration.
    
    - azure Data studio (ADS)

 different ways to migrate databases from On-Prem to Azure SQL
 ---------------------------------------
 - SSMS-> select the database->Tasks->

	>> Extract Data-Tier Application(DACPAC)

	>> Deploy Database to Microsoft Azure SQL Database(BACPAC)

	>> Export Data-Tier application(BACPAC, can store in local disk or Azure storage account ) 

        >> Import data
        >> Export data 
