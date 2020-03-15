# Linux/Unix

##  Common Operations (Linux)

Update packages (Linux):

```bash
apt-get update
apt-get upgrade
apt-get dist-upgrade
apt autoremove
```

##  RSA Setup (Unix)

Generate RSA key:

```bash
ssh-keygen -t rsa
```

Copy public key to host:

```bash
scp ~/.ssh/KEYFILE_NAME.pub USERNAME@HOST:
```

Add public key to host:

```bash
cat ~/KEYFILE_NAME.pub >> ~/.ssh/authorized_keys
```

## SSH Access Setup (Linux):

Install OpenSSH server:

```bash
sudo apt install openssh-server
```

Allow OpenSSH through the computer's *UFW* firewall:

```bash
sudo ufw allow ssh
```

Check *SSH* status:

```bash
sudo systemctl status ssh
```

Restart, start and stop *SSH* server:

```bash
sudo systemctl restart ssh
sudo systemctl start ssh
sudo systemctl stop ssh
```


## Interface Config (Unix):

Check interfaces status (_ip_):

```bash
ifconfig
```
