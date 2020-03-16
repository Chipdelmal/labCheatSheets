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


##  [Setup Samba Server (Linux)](https://help.ubuntu.com/community/How%20to%20Create%20a%20Network%20Share%20Via%20Samba%20Via%20CLI%20%28Command-line%20interface/Linux%20Terminal%29%20-%20Uncomplicated%2C%20Simple%20and%20Brief%20Way%21):

Install samba server:

```bash
sudo apt-get install samba samba-common python-glade2 system-config-samba
```

Set the directory permissions so that anyone can read/write to it:

```bash
sudo chown -R nobody:nogroup FOLDER_PATH
sudo chmod -R 0775 FOLDER_PATH
```

Open the *config* file:

```bash
sudo nano /etc/samba/smb.conf
```

and add the following lines (set *guest* to **no** if authentication is needed, and/or *writable* to **no** with *read only* to **yes** to avoid writing privileges):

```
[SambaShare]
Comment = Samba Shared Directory
path = FOLDER_PATH
writable = yes
guest ok = yes
read only = no
force user = nobody
```

reset the server:

```bash
sudo service smbd restart
```
