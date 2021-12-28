The Kernel exploit methodology is simple;

 Identify the kernel version
 Search and find an exploit code for the kernel version of the target system
 Run the exploit 
    
    
   ### Hints/Notes:

Being too specific about the kernel version when searching for exploits on Google, Exploit-db, or searchsploit
Be sure you understand how the exploit code works BEFORE you launch it. Some exploit codes can make changes on the operating system that would make them unsecured in further use or make irreversible changes to the system, creating problems later. Of course, these may not be great concerns within a lab or CTF environment, but these are absolute no-nos during a real penetration testing engagement.
Some exploits may require further interaction once they are run. Read all comments and instructions provided with the exploit code.
You can transfer the exploit code from your machine to the target system using the SimpleHTTPServer Python module and wget respectively. 
    
    
   ![image](https://user-images.githubusercontent.com/96658935/147586309-0ee97b39-28b5-4bfa-a516-08aa09cb7fdb.png)

    
   # Enumeration
    
  The proc filesystem (procfs) provides information about the target system processes. 
  You will find proc on many different Linux flavours, making it an essential tool to have in your arsenal.

Looking at /proc/version may give you information on the kernel version and additional data such as whether a compiler (e.g. GCC) is installed. 

```bash
cat /proc/version
#This command will show you kernal info
```

[OR]

```bash

uname -a
```



## Exploitation

Goolge the kernel version and see if there is a exploit for it

![image](https://user-images.githubusercontent.com/96658935/147516617-d5188a6a-3a04-4c0b-8de5-966e4c3aaf59.png)


![image](https://user-images.githubusercontent.com/96658935/147516878-cda8dfdb-5f18-4c9b-8be8-0a8b349ea023.png)


The exploit should include the usage 


# Another Example


![image](https://user-images.githubusercontent.com/96658935/147587364-ae4ebe97-8ad1-4e73-9d81-82647c30ec07.png)

Step1 - Get the kernel version


![image](https://user-images.githubusercontent.com/96658935/147587436-ed6d13f6-804d-455e-bf76-62a70d149e67.png)

Step2 - Google it and find a potential privesc exploit

![image](https://user-images.githubusercontent.com/96658935/147587600-82ff3a93-cae3-495b-9b18-f2c552cbd268.png)

They usually have instructions so follow them.

![image](https://user-images.githubusercontent.com/96658935/147587681-e927492a-24e7-4d88-b148-1003bfcf82b7.png)

Step3 - Download the exploit and host a python server to transfer t over to the other machine


![image](https://user-images.githubusercontent.com/96658935/147587853-aa7ecb51-c7cf-49e4-86a1-49e36c92852f.png)

Step4 - Follow the instructions from the exploit


![image](https://user-images.githubusercontent.com/96658935/147587880-a3dfd4d3-2db3-4fda-98e5-b068b3ba765f.png)

you can ssh or just su firefart into teh new account










