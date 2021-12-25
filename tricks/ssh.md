# ssh

## Key Generation

```bash
ssh-keygen -f id_rsa
# private key: id_rsa
# public key: id_rsa.pub
```

## Key Insertion for root user

1. Generate key
2. copy `id_rsa.pub` to `/root/.ssh/authorized_keys`

## Perms Error

1. For private key file:
    1. `chmod 600 id_rsa`
2. For `authorized_keys` file:
    1. `chmod 700 /root/.ssh`
    2. `chmod 700 /root/.ssh/authorized_keys`

## flags for common errors

```bash
# flag for algorithm
-okexAlgorithms=+diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1,diffie-hellman-group1-sha1

# flag for public key
-oPubkeyAcceptedKeyTypes=+ssh-dss
```


## Changing authorized-keys

if text editor doesn't work use echo
```bash
Example: echo "ssh-rsa ....." >> authorized_keys
```

```bash
ssh -i newkey -okexAlgorithms=+diffie-hellman-group-exchange-sha1,diffie-hellman-group14-sha1,diffie-hellman-group1-sha1  192.168.70.42
```

connect wih the private key


