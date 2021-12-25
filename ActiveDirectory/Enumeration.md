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




