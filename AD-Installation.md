## install the adds role
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools

## configure the domain and forest
Install-ADDSForest -DomainName {YOURDOMAINHERE} -InstallDNS

> ref https://www.readandexecute.com/how-to/server-2016/active-directory/installing-active-directory-with-powershell-windows-server-2016/

## disable the windows firewall 
### first get the profile status
Get-NetFirewallProfile | Format-Table Name, Enabled

### disable all 3 profiles
Set-NetFirewallProfile -Profile Domain, Public, Private -Enabled False

> https://www.alitajran.com/disable-windows-firewall-with-powershell/
