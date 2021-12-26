# Enumeration 

## Enumeration of shared folders

* An rsync module is essentially a directory share. These modules can optionally be protected by a password. This options lists the available modules and, optionally, determines if the module requires a password to access:
```bash
nmap -sV --script "rsync-list-modules" -p <PORT> <IP>
```

Manual Rsync

* Once you have the list of modules you have a few different options depending on the actions you want to take and whether or not authentication is required. If authentication is not required you can list a shared folder:
```bash
rsync -av --list-only rsync://192.168.0.123/shared_name
```




