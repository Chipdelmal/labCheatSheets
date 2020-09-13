# Linux/Unix

For a list of useful Linux shortcuts, follow this [link](https://itsfoss.com/ubuntu-shortcuts/).

##  Common Operations (Linux)

Update packages:

```bash
apt-get update
apt-get upgrade
apt-get dist-upgrade
apt autoremove
```

Check interfaces status (_ip_ address):

```bash
ifconfig
```

Install from **run** file:

```bash
chmod +x APP_NAME.run
APP_NAME.run
```

Suspend/Hibernate:

```bash
systemctl suspend
systemctl hibernate
```

Setup scripts to run at time intervals with [crontab](https://help.ubuntu.com/community/CronHowto):

```bash
crontab -e
```

<hr>

## SSH Login to a Host (Unix)

*SSH* with password, or the default *RSA* key (or the one setup in the `~/.ssh/config` file):

```bash
ssh USER_NAME@HOST_ADDRESS_OR_NAME
```

*SSH* with a specific *RSA* key:

```bash
ssh -i ~/.ssh/KEY_FILE USER_NAME@HOST_ADDRESS_OR_NAME
```

To setup the key automatically for a specific host create or open the *config* file:

```bash
nano ~/.ssh/config
```

and add the following to setup the alias and key:

```
Host HOST_ADDRESS_OR_NAME
  HostName ALIAS
  User USER_NAME
  IdentityFile ~/.ssh/KEY_FILE
  PreferredAuthentications publickey
```

In MacOs, the password can be added to the keychain automatically by adding the following lines:

```
  UseKeychain yes
  AddKeysToAgent yes
```


##  [RSA Setup (Unix)](https://linuxize.com/post/how-to-set-up-ssh-keys-on-ubuntu-1804/)

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

Copy public key to clipboard

```bash
xclip -sel clip < ~/.ssh/id_rsa.pub
```

<hr>

## [SSH Server Access Setup (Linux)](https://kb.iu.edu/d/aews)

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
