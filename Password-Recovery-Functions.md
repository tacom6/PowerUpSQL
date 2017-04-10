These functions are used for recovering authentication tokens of varous types.  The roadmap for development is below.  I've included a few links to standalone scripts that have not been integrated yet.
	
|Function Name                 |Description |
|:-----------------------------|:-----------|
|Get-SQLRecoverPwAutoLogon|Grab Windows auto login passwords from the registry through xp_regread.|
|Get-SQLServerPasswordHash|Grab SQL Server login password hashes.  This supports local admin privilege escalation via the -migrate switch.|
	
**Roadmap:**
	
	Get-SQLRecoverPwCredential - https://github.com/NetSPI/Powershell-Modules/blob/master/Get-MSSQLAllCredentials.psm1	
	Get-SQLRecoverPwServerLink - https://github.com/NetSPI/Powershell-Modules/blob/master/Get-MSSQLLinkPasswords.psm1	
	Get-SQLRecoverPWProxyAccount - https://github.com/NetSPI/Powershell-Modules/blob/master/Get-MSSQLAllCredentials.psm1	
	Get-SQLRecoverMasterKey						 
	Get-SQLRecoverMachineKey		
	Get-SQLRecoverPwLsaSecrets
	Get-SQLRecoverPwLogonOn
	Get-SQLRecoverPwVNC