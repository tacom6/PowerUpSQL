These functions can be used for enumerating SQL Server instances.  Discovered instances can then be piped into other PowerUpSQL functions.

|Function Name|Description |
|:--------------------------------|:-----------|
|Get-SQLInstanceFile|Returns SQL Server instances from a file.  One per line.| 
|Get-SQLInstanceLocal|Returns SQL Server instances from the local system based on a registry search.|
|Get-SQLInstanceDomain|Returns a list of SQL Server instances discovered by querying a domain controller for systems with registered MSSQL service principal names.  The function will default to the current user's domain and logon server, but an alternative domain controller can be provided. UDP scanning of management servers is optional.|
|Get-SQLInstanceScanUDP|Returns SQL Server instances from UDP scan results.|
|Get-SQLInstanceScanUDPThreaded|Returns SQL Server instances from UDP scan results and supports threading.|

**Examples:**
	
	Get-SQLInstanceDomain -Verbose | Get-SQLServerInfo -Verbose
	Get-SQLInstanceLocal -Verbose | Get-SQLServerInfo -Verbose
	Get-SQLServerInfo -Verbose -Instance "SQLSERVER1\MYINSTANCE"
	Get-SQLServerInfo -Verbose -Instance "SQLSERVER1\MYINSTANCE" -Username MyUser -Password MyPassword
	Get-SQLServerInfo -Verbose -Instance "SQLSERVER1\MYINSTANCE" -Credential MyUser
	
**Roadmap:**
	
	Get-SQLInstanceScanTCP - Returns SQL Server instances from TCP scan results.
	Get-SQLInstanceBroadcast - Returns SQL Server instances from UDP broadcast.
	Get-SQLInstanceAzure - Returns SQL Server instances from Azure environments.
	Get-SQLInstanceAzureFuzz - Returns SQL Server instances from Azure environments via blind dictionary attack. (x.databases.windows.net)

