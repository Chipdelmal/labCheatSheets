#  [Samba (Linux)](https://help.ubuntu.com/community/How%20to%20Create%20a%20Network%20Share%20Via%20Samba%20Via%20CLI%20%28Command-line%20interface/Linux%20Terminal%29%20-%20Uncomplicated%2C%20Simple%20and%20Brief%20Way%21):

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
