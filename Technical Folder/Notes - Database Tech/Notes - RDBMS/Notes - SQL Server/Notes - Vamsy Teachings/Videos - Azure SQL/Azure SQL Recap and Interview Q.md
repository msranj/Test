## Azure SQL Recap and Interview Questions
Reference: https://drive.google.com/file/d/1ggnY1Pt3RFcucQOHrnn6tafZlfPyFnpH/view?usp=drive_link

connectivity between Azure VM's
-----------------------------------
1. Point to site
2. site to site

Interview questions:
------------------------
**1. Can we create clusters, Always On on Azure MI instance?**
- No, we cant. as there is No Windows OS on Paas (azure MI).

**2. Can we restore .bak files to Azure MI?**
- Yes (its LRS - Auto-complete mode & Continous modes)

**3. As a DBA, what cloud platform will you suggest?**
	- VM
	- Azure SQL
	- Azure MI

- Approach 1: ask questions on Kind of workloads on on-prem. 
        2 types of workloads
        1. CPU Bound
        2. IOPS bound

### Tools that can help
--------------------------

- Azure Data Studio: helps choose the right size of DB infra.
	
        -- if you select Azure VM, it will folder to share perform data i.e assessment will run for 10 mins. (iterate for 2 trials Minimum i.e during business hrs & non-business hrs)
	
4. Vendor approach DBA team, there is already Always on configured in on-prem, can we use PAAS platform as Replica? (azure SQL or Azure MI)
    - For Azure SQL: Not possible
    - For Azure MI: supports only SQL 2016 using Distributed AOAG.
    - if SQL 2022 is on-prem, then we can fail over & Failback to Azure MI.

5. Geo-replica & Auto-failover groups.
    - Geo-replica is same for azure SQL: Supports HA & DR on same region.

    - Azure MI: it is Auto-failover groups. does not support HA,but only DR on different region. since HA is in-built here.

Note:
1. DB Migration: From SQL 2016, we can migrate DB's to Azure MI using Link feature, here Azure MI will act as a Replica for Always On.

2. if new app needs windows auth, Azure MI supports, but not Azure SQL.

3. we cannot take DB's offline in Azure SQL & Azure MI.

4. Linked features: only SQL server providers supported in Azure MI(No Oracle,MySQL etc since Paas does not have access to OS). Azure SQL does not support.

5. Replication: Azure MI can act like Distributor, Publisher, subscriber.
Azure SQL: can act like Subscriber.

6. Always on : 
Azure MI has in-built Always on, we need not configure. 
    (
    >> Business critical model uses in-builtAlways on, we can use one of the replica as secondary.

    >> General purpose mode: we dont  have Always on.
    )
Azure SQL : Geo-replica not similar to Always on.

7. Azure SQL: 
- Extended events are present inside the DB folder.
- cross db queries are not possible.
- cannot be set below parameters.
	-- collation
	-- time zone.
