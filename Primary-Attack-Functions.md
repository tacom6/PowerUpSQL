These are the functions used to quickly dump database information, audit for common vulnerabilities, and attempt to obtain sysadmin privileges.

|Function Name                 |Description |
|:-----------------------------|:-----------|
|Invoke-SQLDumpInfo|This can be used to dump SQL Server and database information to csv or xml files.  This can be handy for doing a quick inventory of databases, logins, privileges etc.|
|Invoke-SQLAudit|This can be used to review the SQL Server and databases for common configuration weaknesses and provide a vulnerability report along with recommendations for each item.|
|Invoke-SQLEscalatePriv|This can be used to obtain sysadmin privileges via identified configuration weaknesses.|

**Examples:**

	Get-SQLInstanceDomain -Verbose | Invoke-SQLDumpInfo -Verbose
	Get-SQLInstanceLocal -Verbose | Invoke-SQLAudit -Verbose
	Invoke-SQLEscalatePriv -Verbose -Instance "SQLSERVER1\MyInstance" -Username MyUser -Password MyPassword