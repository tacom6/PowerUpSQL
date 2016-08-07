These functions are used for maintaining access to the SQL Server using various methods.  The roadmap for development is below.  I've included a few links to standalone scripts that have not been integrated yet.

|Function Name                 |Description |Requires Sysadmin Privs|
|:-----------------------------|:-----------|:---------|
|Get-SQLPersistRegRun|This function will use the xp_regwrite procedure to setup an executable to automatically run when users log in.  The specific registry key is HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run. | Yes |
|Get-SQLPersistRegDebugger|This function uses xp_regwrite to configure a debugger for a provided executable (utilman.exe by default), which will run another provided executable (cmd.exe by default) when it’s called.  It is commonly used to create RDP backdoors.  The specific registry key is HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\[EXE].|Yes|

**Roadmap:**
	
	Get-SQLPersistAssembly						  
	Get-SQLPersistSp						
	Get-SQLPersistSpStartup	- https://github.com/nullbind/Powershellery/blob/master/Stable-ish/MSSQL/Invoke-SqlServer-Persist-StartupSp.psm1					 
	Get-SQLPersistTriggerDml					  
	Get-SQLPersistTriggerDdl - https://github.com/nullbind/Powershellery/blob/master/Stable-ish/MSSQL/Invoke-SqlServer-Persist-TriggerDDL.psm1					  
	Get-SQLPersistTriggerLogon - https://github.com/nullbind/Powershellery/blob/master/Stable-ish/MSSQL/Invoke-SqlServer-Persist-TriggerLogon.psm1					
	Get-SQLPersistView							   
	Get-SQLPersistInternalObject				
	Get-SQLPersistAgentJob						 
	Get-SQLPersistXstatus						   
	Get-SQLPersistSkeletonKey					  
	Get-SQLPersistFullPrivLogin					
	Get-SQLPersistImpersonateSysadmin	