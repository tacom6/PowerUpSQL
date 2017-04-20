These are essentially helper functions.  Some of them are used by other PowerUpSQL functions, but all of them can be run independently.

|Function Name                 |Description |
|:-----------------------------|:-----------|
|Get-SQLConnectionObject | Creates a object for connecting to SQL Server.|
|Get-SQLFuzzObjectName | Enumerates objects based on object id using OBJECT_NAME() and only the Public role.|	
|Get-SQLFuzzDatabaseName | Enumerates databases based on database id using DB_NAME() and only the Public role.|
|Get-SQLFuzzServerLogin | Enumerates SQL Server Logins based on login id using SUSER_NAME() and only the Public role.|
|Get-SQLFuzzDomainAccount | Enumerates domain groups, computer accounts, and user accounts based on domain RID using SUSER_SNAME() and only the Public role.  Note: In a typical domain 10000 or more is recommended for the EndId.|
|Get-ComputerNameFromInstance | Parses computer name from a provided instance.|
|Get-SQLServiceLocal | Returns local SQL Server services.|
|Create-SQLFileXpDll | Used to create CPP DLLs with exported functions that can be imported as extended stored procedures in SQL Server. Supports arbitrary command execution.|
|Get-DomainSpn | Returns a list of SPNs for the target domain. Supports authentication from non domain systems.|
|Get-DomainObject | Used to query domain controllers via LDAP.  Supports alternative credentials from non-domain system.|
|Get-SQLStoredProcedureSQLi|Returns stored procedures using dynamic SQL and the "WITH EXECUTE AS OWNER" clause. If the stored procedure is vulnerable to SQLi it may be possible to impersonate the procedure owner.
|Get-SQLServerLoginDefaultPw|Based on the instance name, test if SQL Server is configured with default passwords.
|Create-SQLFileXpDll|Used to generate DLLs that can be imported to create a custom stored procedure that executes OS commands
|Create-SQLFileCLRDll|Used to generate DLLs that can be imported to create a CLR stored procedure that executes OS commands.  It also generate a file that can generate TSQL code for creating the procedure without the DLL.

**Examples:** 

	Get-SQLFuzzServerLogin -Verbose -Instance "SQLSVR1\Instance1"

**Roadmap:**

	Get-SQLFuzzDatabase
	Get-SQLFuzzSchema
	Get-SQLDatabaseOrphanUser             		
	Get-SQLDatabaseUser - add fuzzing option
	Get-SQLStoredProcedureEncrypted		
	Get-SQLDecryptedStoreProcedure            	
	Get-SQLDownloadFile				
	Get-SQLDownloadFileAdHocQuery			
	Get-SQLDownloadFileAssembly             	
	Get-SQLDownloadFileBulkInsert			
	Get-SQLDownloadFileServerLine			
	Get-SQLDownloadFileXpCmdshell			
	Get-SQLInstalledSoftware			
	Get-SQLServerLogin - add fuzzing option		
	Get-SQLUploadFile				
	Get-SQLUploadFileAdHocQuery             	
	Get-SQLUploadFileAgent				
	Get-SQLUploadFileAssembly             		
	Get-SQLUploadFileServerLink             	
	Get-SQLUploadFileXpCmdshell             	
	Invoke-SqlOSCmdAdHoQueryMd			            	
	Invoke-SqlOSCmdAgentAnalysis			
	Invoke-SqlOSCmdAgentCmdExec			
	Invoke-SqlOSCmdAgentPs		
	Invoke-SqlOSCmdAgentActiveX	
	Invoke-SqlOSCmdAgentVbscript			
	Invoke-SqlOSCmdAgentJsscript
	Invoke-SqlOSCmdAgentOther
	Invoke-SqlOSCmdAssemblyXP             		
	Invoke-SqlOSCmdServerLinkMd			
	Invoke-SqlOSCmdSsisExecuteProcessTask
	Enable-FullRegRead
	Disable-FullRegRead