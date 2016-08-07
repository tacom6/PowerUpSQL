
These functions are used to test connections, execute SQL Server queries, and execute OS commands.  All other functions use these core functions.  However, they can also be executed independently. 

|Function Name                 |Description |
|:-----------------------------|:-----------|
|Get-SQLConnectionTest|Tests if the current Windows account or provided SQL Server login can log into an SQL Server.
|Get-SQLConnectionTestThreaded|Tests if the current Windows account or provided SQL Server login can log into an SQL Server and supports threading.|
|Get-SQLQuery|Executes a query on target SQL servers.|
|Get-SQLQueryThreaded|Executes a query on target SQL servers and supports threading.|
|Invoke-SQLOSCmd|Execute command on the operating system as the SQL Server service account using xp_cmdshell. Supports threading, raw output, and table output.|

**Examples:**

	Get-SQLInstanceDomain -Verbose | Get-SQLConnectionTestThreaded -Verbose -Threads 10 
	Get-SQLInstanceDomain -Verbose | Invoke-SQLOSCmd -Verbose -Threads 10 -Command "whoami"