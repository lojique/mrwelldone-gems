# Enumeration


## GoBuster

```bash
gobuster dir -u http://10.10.10.121/ -w /usr/share/dirb/wordlists/common.txt
```

![image](https://user-images.githubusercontent.com/96658935/147843952-593eeb03-0ec5-4018-bd1a-187543421f27.png)



## DNS SubDomain Enumeration

* First go to /etc/resolv.conf and configure a site you want to enumerate subdomains for.

![image](https://user-images.githubusercontent.com/96658935/147844021-3cb46ba7-e0e3-4c20-b53d-aeef65469a24.png)


* Download Seclists

```bash
git clone https://github.com/danielmiessler/SecLists

```

Run it

```bash
└─# gobuster dns -d inlanefreight.com -w /root/tools/SecLists/Discovery/DNS/namelist.txt
```


![image](https://user-images.githubusercontent.com/96658935/147844032-f2a217f8-ec73-4b65-a6a9-89c6397e78c5.png)


## Banner Grabbing / Web Server Headers 

```bash
curl -IL http://167.99.202.131:32630 
```

![image](https://user-images.githubusercontent.com/96658935/147844123-389b6aa8-2f5f-45ab-9039-90c33ff0546f.png)


* Can also view source code


