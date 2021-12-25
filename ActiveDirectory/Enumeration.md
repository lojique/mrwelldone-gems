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


