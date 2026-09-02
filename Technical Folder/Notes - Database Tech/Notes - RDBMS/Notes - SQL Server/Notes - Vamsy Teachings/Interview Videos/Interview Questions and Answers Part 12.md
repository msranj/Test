
# Interview Questions and Answers Part 12


#### Video link: https://drive.google.com/file/d/1CrwPvZfliqzaY6iBz56ndtt86jcBhdt9/view?usp=drive_link

#### Reference links:
https://www.mssqltips.com/sqlservertip/3150/adding-sql-server-alwayson-availability-groups-to-existing-failover-clusters/

https://techcommunity.microsoft.com/blog/sqlserver/sql-network-interfaces-error-26---error-locating-serverinstance-specified/383277

https://www.sqlservercentral.com/articles/tempdb-growth-due-to-version-store-on-alwayson-secondary-server

#### Video timeline
**0:00 - 2:15** // 

Question1: tell me about your experience with Always on and cluster installation.

**2:17 - 12:00** // 

Question2: Suppoše we have 2 node SQL Server Clusters and another stand alone sql server instance, So can we create an Availability group? 

**12:00 - 19:00** //

Question 3: what about the shared disks in WSFC?

**19:02 - 25:35**// 

Question 4: when configuring 3 Node AlwaysON AG, when trying to add 1 of the instance which is up & we can connect it via SSMS and not RDP but when doing the configuration it is showing unable to connect to server. 

What is the issue and what will you do to fix it? 

### Explanation
**0:00 - 2:15** //

Question1: tell me about your experience with Always on and cluster installation.

Answer1: you can tell like
- Always on was introduced in SQL server 2012 version and it is a replacement for mirroring and clustering. It is available for both HA & DR.
- Here, clustering is an instance level feature, always on is database level feature.
- Clustering is mainly for HA, not for DR. Always on is both for HA & DR. 
- Clustering requires shared disks, always on does not require shared disks.

**2:17 - 12:00** // 

**Question2**: Suppoše we have 2 node SQL Server Clusters and another stand alone sql server instance, So can we create an Availability group? 

**Answer**: we need to

- Add always on features on existing cluster nodes and add failover cluster on secondary data center (assume Node 3).
- Come to primary & add node in cluster configuration.
- Now node 3 which is added to cluster should NOT be the owner of the current Failover cluster.
- Why? Because if Node 3 is added, then we will get error while establishing AG from SSMS.

![error 19405](https://i.sstatic.net/Y1DN1.png)
Also,make sure to remove the new node 3 from preferred owners & possible owners.

- Also,make sure to remove the new node 3 from preferred owners & possible owners.

**12:00 - 19:00** //
Question 3: what about the shared disks in WSFC?
Answer: 

**19:02 - 25:35** // 

**Question 4**: 

>> when configuring 3 Node AlwaysON AG, when trying to add 1 of the instance(i.e adding an existing replica to the configuration) which is up & we can connect it via SSMS and not RDP but when doing the configuration it is showing unable to connect to the server. What is the issue and what will you do to fix it? 

**Answer**: 

issue happens with named instances, not default instances.

We need to use the port number while connecting. 
I.e. SSMS->options->connect with port.

>> we have a NAMED instance that connects with port 1433, unable to connect when I am trying to connect to that instance without a port number 1433, but connect with mention of port 1433.

Answer: we need to open UDP port 1434

Reference: https://techcommunity.microsoft.com/blog/sqlserver/sql-network-interfaces-error-26---error-locating-serverinstance-specified/383277


**24:50 - 39:16**//

Question 5: 

    5.1) there is a running job that completes in 15 minutes, there were NO changes made but it is taking very long today. How will you fix this?

    5.2) app team says that the server was running fine till yesterday, but today all jobs are taking a long time to complete, how do you approach this issue to fix it?

Answer: 

- Check if Rebuild/Reorg jobs are running.
- Check for blockings.
- If there are any dataloads that are happening on tables that are associated with slow queries.
- Check if any schema changes. (check Schema change histories)
- Check if jobs got any changes (from msdb)
- For any night ETL jobs, better disable non-clustered indexes, load the data & re-enable the non-clustered indexes.
- Check if there is Parameter sniffing


**39:35** - end of video//

**Question 6**: 

Tempdb file got filled up in Always on secondary replica during huge transactions. How will you add files & what is your approach?

All db on secondary replica will operate in snapshot isolation level by default and you cannot override this option.

https://www.sqlservercentral.com/articles/tempdb-growth-due-to-version-store-on-alwayson-secondary-server

#check tempdb growth
```
SELECT GETDATE() AS runtime,
SUM(user_object_reserved_page_count) * 8 AS usr_obj_kb,
SUM(internal_object_reserved_page_count) * 8 AS internal_obj_kb,
SUM(version_store_reserved_page_count) * 8 AS version_store_kb,
SUM(unallocated_extent_page_count) * 8 AS freespace_kb,
SUM(mixed_extent_page_count) * 8 AS mixedextent_kb
FROM sys.dm_db_file_space_usage;
```

again, 2 cases here to note. 

    1. If an issue has already happened we need to check DMV's or any other meta table that has data.
-- check sys.sysprocesses to find long running SPID that is contributing to tempdb growth and kill (if required)

    2. If an issue is happening now, sp_whoisactive will be helpful.


Q. In Always On, DB went into Suspected mode, what is troubleshooting step?

Ans: 
2 Scenario Answers

Scenario 1
***************

1. transaction Log file full issue, disk space issue.
so, 
    1.1 Firstly we need to failover to secondary replica.

    1.2 as per MSFT URL shown below, we need to remove the AG group itself where the db belongs. here the db should be in secondary role only.

    1.3 put the db in emergenc mode & remaining steps. 

Note:
https://jonshaulis.com/index.php/2019/03/26/sql-server-database-in-suspect-mode/

https://learn.microsoft.com/en-us/troubleshoot/sql/database-engine/availability-groups/alwayson-availability-databases-recovery-pending-suspect









