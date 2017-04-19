These are the functions used to quickly dump database information, audit for common vulnerabilities, and attempt to obtain sysadmin privileges.

|Function Name                 |Description |Obtains Sysadmin Privs|
|:-----------------------------|:-----------|:-----------|
|Invoke-SQLDumpInfo|This can be used to dump SQL Server and database information to csv or xml files.  This can be handy for doing a quick inventory of databases, logins, privileges etc.| No |
|Invoke-SQLAudit|This can be used to review the SQL Server and databases for common configuration weaknesses and provide a vulnerability report along with recommendations for each item.| No |
|Invoke-SQLEscalatePriv|This can be used to obtain sysadmin privileges via identified configuration weaknesses.| Yes|
|Invoke-SQLImpersonateService | This can be used to impersonate a provided SQL Server service account using a provided SQL Server instance as a local admin . After impersonation any PowerUpSQL command can be run in the sysadmin context.| Yes |
|Invoke-SQLImpersonateServiceCmd | This can be used to run any OS command as the target SQL Server service account. It can be used to provide a local administrator with sysadmin privileges.| Yes |
|Invoke-SQLOSCmd|Run OS commands as the SQL Server service account via xp_cmdshell. Typically requires sysadmin privileges.|No|
|Invoke-SQLOSCmdCLR|Run OS commands as the SQL Server service account via CLR assemblies.  Does not require reading a DLL from disk. Typically requires sysadmin privileges.|No

**Examples:**

	Get-SQLInstanceDomain -Verbose | Invoke-SQLDumpInfo -Verbose
	Get-SQLInstanceLocal -Verbose | Invoke-SQLAudit -Verbose
	Invoke-SQLEscalatePriv -Verbose -Instance "SQLSERVER1\MyInstance" -Username MyUser -Password MyPassword
	Invoke-SQLImpersonateServiceCmd -Verbose -Instance SQLServer1\STANDARDDEV2014 -EngineOnly -Exe 'PowerShell -c "notepad.exe"'
	Invoke-SQLImpersonateServiceCmd -Verbose -Instance SQLServer1\STANDARDDEV2014 -EngineOnly