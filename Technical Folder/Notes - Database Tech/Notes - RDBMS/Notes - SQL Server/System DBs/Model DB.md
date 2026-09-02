## Model DB

The model database is used as the template for all databases created on an instance of SQL Server. Because tempdb is created every time SQL Server is started, the model database must always exist on a SQL Server system. 

Certain properties can be changed in MSDB to reflect in newly created databases.

		○ Auto_shrink
		○ Recovery model
		○ Auto_update_statistics
		○ Encrytpion (on / off)
        ○ Page_verify
        