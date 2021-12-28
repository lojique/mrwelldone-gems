The Kernel exploit methodology is simple;

 Identify the kernel version
 Search and find an exploit code for the kernel version of the target system
 Run the exploit 
    
    
   ### Hints/Notes:

Being too specific about the kernel version when searching for exploits on Google, Exploit-db, or searchsploit
Be sure you understand how the exploit code works BEFORE you launch it. Some exploit codes can make changes on the operating system that would make them unsecured in further use or make irreversible changes to the system, creating problems later. Of course, these may not be great concerns within a lab or CTF environment, but these are absolute no-nos during a real penetration testing engagement.
Some exploits may require further interaction once they are run. Read all comments and instructions provided with the exploit code.
You can transfer the exploit code from your machine to the target system using the SimpleHTTPServer Python module and wget respectively. 
    
    
   # Enumeration
    
  The proc filesystem (procfs) provides information about the target system processes. 
  You will find proc on many different Linux flavours, making it an essential tool to have in your arsenal.

Looking at /proc/version may give you information on the kernel version and additional data such as whether a compiler (e.g. GCC) is installed. 

```bash
cat /proc/version
#This command will show you kernal info
```


## Exploitation

Goolge the kernel version and see if there is a exploit for it

![image](https://user-images.githubusercontent.com/96658935/147516617-d5188a6a-3a04-4c0b-8de5-966e4c3aaf59.png)


![image](https://user-images.githubusercontent.com/96658935/147516878-cda8dfdb-5f18-4c9b-8be8-0a8b349ea023.png)


The exploit should include the usage 


