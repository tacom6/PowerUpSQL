These functions are used for identifying weak configurations that can lead to unauthorized access.  Invoke-SQLAudit can be used to run all of them at once. Also, all of the audit functions support an exploit flag.  In most cases that means the script will try to add your login to the sysadmin server role.

|Function Name                 |Description |Obtains Sysadmin Privs|
|:-----------------------------|:-----------|:---------|
|Invoke-SQLAuditPrivCreateProcedure|Check if the current login has the CREATE PROCEDURE permission.  Attempt to use permission to obtain sysadmin privileges.|No|
|Invoke-SQLAuditPrivImpersonateLogin|Check if the current login has the IMPERSONATE permission on any sysadmin logins. Attempt to use permission to obtain sysadmin privileges.|Yes|
|Invoke-SQLAuditPrivServerLink|Check if SQL Server links exist that are preconfigured with alternative credentials that can be impersonated. Provide example queries for execution on remote servers.|Yes|
Invoke-SQLAuditPrivDbChaining|Check if database ownership chaining is enabled at the server or databases levels.|No|
|Invoke-SQLAuditPrivTrustworthy|Check if any database have been flagged as trusted.|No|
|Invoke-SQLAuditPrivXpDirtree|Checks if the xp_dirtree stored procedure is executable.  Uses Inveigh to obtain password hash for the SQL Server service account. Note: Capture likelihood is better when longer timeouts are set.|Yes|
|Invoke-SQLAuditPrivXpFileexist|Checks if the xp_fileexist stored procedure is executable.  Uses Inveigh to obtain password hash for the SQL Server service account. Note: Capture likelihood is better when longer timeouts are set.|Yes|
|Invoke-SQLAuditRoleDbDdlAdmin|Check if the current login has the DB_DdlAdmin role in any databases.  Attempt to use permission to obtain sysadmin privileges.|No|
|Invoke-SQLAuditRoleDbOwner|Check if the current login has the DB_OWNER role in any databases.  Attempt to use permission to obtain sysadmin privileges.|Yes|
|Invoke-SQLAuditSampleDataByColumn|Check if the current login can access any database columns that contain the word password. Supports column name keyword search and custom data sample size.  For better data searches use Get-SQLColumnSampleData.|No|
|Invoke-SQLAuditWeakLoginPw|This can be used for online dictionary attacks. It also support auto-discovery of SQL Logins for testing if you already have a least privilege account.|Yes|

**Examples:** 

	Get-SQLInstanceLocal | Invoke-SQLAuditPrivImpersonateLogin -Verbose
	
**Roadmap:**
	
	Create-SqlAuditPrivCreateStartUpProc
	Invoke-SQLAuditCrawlOwnershipChain	
	Invoke-SQLAuditCrawlServerLink
	Invoke-SQLAuditDictionaryAttackOffline
	Invoke-SQLAuditDictionaryAttackOnline
	Invoke-SQLAuditImpersonateDatabaseUser
	Invoke-SQLAuditPrivAdministerBulkOps
	Invoke-SQLAuditPrivAgentJob 
	Invoke-SQLAuditPrivAlterAssembly	
	Invoke-SQLAuditPrivAlterServerLogin
	Invoke-SQLAuditPrivAlterServerRole
	Invoke-SQLAuditPrivControlServer
	Invoke-SQLAuditPrivControlServer
	Invoke-SQLAuditPrivCreateAssembly -CLR -Binary -C
	Invoke-SQLAuditPrivCreateStartUpSP
	Invoke-SQLAuditPrivCreateTriggerDDL
	Invoke-SQLAuditPrivCreateTriggerDML
	Invoke-SQLAuditPrivCreateTriggerLOGON
	Invoke-SQLAuditPrivExternalAssembly
	Invoke-SqlAuditPrivInjectUncPath - https://github.com/nullbind/Powershellery/blob/master/Stable-ish/MSSQL/Get-SQLServiceAccountPwHash.ps1
	Invoke-SqlAuditPrivXpCmdshell
	Invoke-SQLAuditRoledbAccessAdmin	
	Invoke-SQLAuditRoledbSecurityAdmin
	Invoke-SQLAuditSQLi-ImpersonateDatabaseUser - https://blog.netspi.com/hacking-sql-server-stored-procedures-part-3-sqli-and-user-impersonation/
	Invoke-SQLAuditSQLi-ImpersonateLogin - https://blog.netspi.com/hacking-sql-server-stored-procedures-part-3-sqli-and-user-impersonation/
	Invoke-SQLAuditSQLi-ImpersonateSignedSp - https://blog.netspi.com/hacking-sql-server-stored-procedures-part-3-sqli-and-user-impersonation/
	Invoke-SQLOSAdmintoSysadmin - https://github.com/nullbind/Powershellery/blob/master/Stable-ish/MSSQL/Invoke-SqlServerServiceImpersonation-Cmd.ps1
	Invoke-SQLFindSharedSa   
	Invoke-SQLFindDefaultPasswords
