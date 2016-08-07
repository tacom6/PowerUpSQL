### Installing the Module
* Option 1: Install it from the PowerShell Gallery.  This requires local administrative privileges and will permanently install the module.

    `Install-Module -Name PowerUpSQL`

* Option 2: Download the project and import it.  This does not require administrative privileges and will only be imported into the current session.  However, it may be blocked by restrictive execution policies.

    `Import-Module PowerUpSQL.psd1`
* Option 3: Load it into a session via a download cradle.  This does not require administrative privileges and will only be imported into the current session.  It should not be blocked by executions policies.

    `IEX(New-Object System.Net.WebClient).DownloadString("https://raw.githubusercontent.com/NetSPI/PowerUpSQL/master/PowerUpSQL.ps1")`

     Note: To run as an alternative domain user, use the runas command to launch PowerShell first. 

    `runas /noprofile /netonly /user:domain\user PowerShell.exe`

### Getting Command Help
* To list functions from the module, type: `Get-Command -Module PowerUpSQL`
* To list help for a function, type: `Get-Help FunctionName`