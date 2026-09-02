### Day 1 Demo Session.
Video - https://drive.google.com/file/d/1tPHo8urHwABV_5zjwnWeJrssiMgnhmoV/view

Troubleshooting scenario:
------------------------------
issue: client is unable to use Azure SQL instance from local machine SSMS. error is 

```
Cannot open server 'myserver.database.windows.net' requested by the login.
Client is not allowed to access the server. (Microsoft SQL Server, Error: 40914)
```
![error 40914](https://i.sstatic.net/hNqDm.png)

#### what is the approach?

Approach:1
under the Networking Section
- Check the box: 

    Allow Azure services & resources to access this server
        
        (all connection including external services, Internal Azure Storage, azure network  etc).

