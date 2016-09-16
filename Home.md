## ![alt tag](https://github.com/NetSPI/PowerUpSQL/blob/master/scripts/PowerUpSQL-Large.png)
### PowerUpSQL: A PowerShell Toolkit for Attacking SQL Server

The PowerUpSQL module includes functions that support SQL Server discovery, auditing for common weak configurations, and privilege escalation on scale.  It is intended to be used during internal penetration tests and red team engagements. However, PowerUpSQL also includes many functions that could be used by administrators to quickly inventory the SQL Servers in their ADS domain.

**PowerUpSQL was designed with six objectives in mind:**
* Easy Server Discovery: Discovery functions can be used to blindly identify local, domain, and non-domain SQL Server instances on scale.
* Easy Server Auditing: The Invoke-SQLAudit function can be used to audit for common high impact vulnerabilities and weak configurations using the current login's privileges.  Also, Invoke-SQLDumpInfo can be used to quickly inventory databases, privileges, and other information.
* Easy Server Exploitation: The Invoke-SQLEscalatePriv function attempts to obtain sysadmin privileges using identified vulnerabilities. 
* Scalability: Multi-threading is supported on core functions so they can be executed against many SQL Servers quickly.
* Flexibility: PowerUpSQL functions support the PowerShell pipeline so they can be used together, and with other scripts.
* Portability: Default .net libraries are used and there are no dependencies on SQLPS or the SMO libraries. Functions have also been designed so they can be run independently. As a result, it's easy to use on any Windows system with PowerShell v3 installed.


### Module Information
* Author: Scott Sutherland (@_nullbind), NetSPI - 2016
* Contributors: Antti Rantasaari and Eric Gruber (@egru)
* License: BSD 3-Clause
* Required Dependencies: None