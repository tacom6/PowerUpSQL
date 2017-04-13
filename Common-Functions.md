These functions are used for common information gathering tasks.  Similar to core functions, the common functions can be executed by themselves, but are also used by other functions in the PowerUpSQL module.

|Function Name                 |Description |
|:-----------------------------|:-----------|
|Get-SQLAgentJob|Returns a list of SQL Agent jobs from target servers that includes the command to be executed.|
|Get-SQLAuditDatabaseSpec|Returns Audit database specifications from target SQL Servers.|
|Get-SQLAuditServerSpec|Returns Audit server specifications from target SQL Servers.|
|Get-SQLColumn|Returns column information from target SQL Servers. Supports keyword search.|
|Get-SQLColumnSampleData|Returns column information from target SQL Servers. Supports search by keywords, sampling data, and validating credit card numbers.|
|Get-SQLColumnSampleDataThreaded|Returns column information from target SQL Servers. Supports search by keywords, sampling data, and validating credit card numbers. Supports host threading.|
|Get-SQLDatabase|Returns database information from target SQL Servers.|
|Get-SQLDatabaseThreaded|Returns database information from target SQL Servers. Supports host threading.|
|Get-SQLDatabasePriv|Returns database user privilege information from target SQL Servers.|
|Get-SQLDatabaseRole|Returns database role information from target SQL Servers.|
|Get-SQLDatabaseRoleMember|Returns database role member information from target SQL Servers.|
|Get-SQLDatabaseSchema|Returns schema information from target SQL Servers. |	
|Get-SQLDatabaseUser|Returns database user information from target SQL Servers.|
|Get-SQLServerConfiguration|Returns configuration settings from sp_configure.  Output includes advanced options if the connecting user is a sysadmin.|
|Get-SQLServerCredential|Returns credentials from target SQL Servers.|
|Get-SQLServerInfo|Returns basic server and user information from target SQL Servers.|
|Get-SQLServerInfoThreaded|Returns basic server and user information from target SQL Servers. Supports host threading.|
|Get-SQLServerLink|Returns link servers from target SQL Servers.|
|Get-SQLServerLinkCrawl|Crawls linked servers and supports SQL query and OS command execution.|
|Get-SQLServerLogin|Returns logins from target SQL Servers.|
|Get-SQLServerPriv|Returns SQL Server login privilege information from target SQL Servers.|
|Get-SQLServerRole|Returns SQL Server role information from target SQL Servers.|
|Get-SQLServerRoleMember|Returns SQL Server role member information from target SQL Servers.|
|Get-SQLServiceAccount|Returns a list of service account names for SQL Servers services by querying the registry with xp_regread.  This can be executed against remote systems.|
|Get-SQLSession|Returns active sessions from target SQL Servers.|
|Get-SQLStoredProcure|Returns stored procedures from target SQL Servers.|	
|Get-SQLSysadminCheck|Check if login is has sysadmin privilege on the target SQL Servers.|
|Get-SQLTable|Returns table information from target SQL Servers.|
|Get-SQLTriggerDdl|Returns DDL trigger information from target SQL Servers.  This includes logon triggers.|
|Get-SQLTriggerDml|Returns DML trigger information from target SQL Servers.|
|Get-SQLView|Returns view information from target SQL Servers.|
|Get-SQLLocalAdminCheck|Checks if the current Windows user has local administrator privileges and is running in an elevated process on the system.|

**Examples:**

	Get-SQLInstanceLocal | Get-SQLDatabase -Verbose -NoDefaults
	Get-SQLInstanceLocal | Get-SQLColumnSampleData -Keywords "account,credit,card" -SampleSize 5 -ValidateCC 

**Roadmap:**

	Get-SQLSubSystem - Returns sub systems from target SQL Servers that are supported by the job agent.
	Get-SQLProxyAccount - Returns proxy accounts from target SQL Servers.
	Get-SQLTempObject - Returns temp objects from target SQL Servers.	
	Get-SQLCachePlan - Returns cache plans from target SQL Servers.	
	Get-SQLQueryHistory - Returns recent query history from target SQL Servers.	
	Get-SQLHiddenSystemObject - Returns hidden system objects from target SQL Servers.	 