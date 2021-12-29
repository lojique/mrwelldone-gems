The sudo command, by default, allows you to run a program with root privileges. 
Under some conditions, system administrators may need to give regular users some flexibility on their privileges.
For example, a junior SOC analyst may need to use Nmap regularly but would not be cleared for full root access.
In this situation, the system administrator can allow this user to only run Nmap with root privileges while keeping its regular privilege level throughout the rest of the system. 

Any user can check its current situation related to root privileges using the sudo -l command.

```bash
sudo -l
```
![image](https://user-images.githubusercontent.com/96658935/147517838-7a810c87-32c1-4935-8a0f-5ab955119914.png)



https://gtfobins.github.io/ is a valuable source that provides information on how any program, on which you may have sudo rights, can be used. 

Once you see what commands can be ran with sudo then go to gtfobins



![image](https://user-images.githubusercontent.com/96658935/147517927-40d7c4d7-20b8-43bf-a1ea-ca87e4ff7260.png)



![image](https://user-images.githubusercontent.com/96658935/147517899-e447a05c-4bdf-4844-aafc-8df4492c6634.png)
