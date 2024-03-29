# Server-Related

SSH into the server:

```bash
ssh USERNAME@marshall-lab-cal.berkeley.edu
```

Disconnect from the server:

```bash
exit
```


Copy file **from server**:

```bash
scp -p USERNAME@marshall-lab-cal.berkeley.edu:SERVER_SOURCE_PATH LOCAL_DESTINATION_PATH
```

Copy folder **from server** (recursive):

```bash
scp -rp USERNAME@marshall-lab-cal.berkeley.edu:SERVER_SOURCE_PATH LOCAL_DESTINATION_PATH
```


Copy file **to server**:

```bash
scp -p LOCAL_DESTINATION_PATH USERNAME@marshall-lab-cal.berkeley.edu:SERVER_SOURCE_PATH
```

Copy folder **to server** (recursive):

```bash
scp -rp LOCAL_DESTINATION_PATH USERNAME@marshall-lab-cal.berkeley.edu:SERVER_SOURCE_PATH
```

Copy files that match extension **from server**:

```bash
scp USERNAME@marshall-lab-cal.berkeley.edu:SERVER_SOURCE_PATH/*.png LOCAL_DESTINATION_PATH
```

Download list of files in txt file (separated by line) to local:

```bash
for i in `cat FILE_WITH_NAMES.txt`; do scp "USERNAME@marshall-lab-cal.berkeley.edu:/PATH_TO_REMOTE/${i}" PATH_TO_LOCAL; done
```

Check folder size:

```bash
du -h --max-depth=0 /path/to/directory
```

Delete folder recursively (DESTRUCTIVE):

```bash
rm -R FOLDER_PATH
```

Delete long lists with pattern:

```bash
find . -name '*PATTERN*' | xargs rm
```

Check disk usage
```bash
df -h
```

or 

```bash
ncdu
```

<hr>

## Processes

Check I/O:

```bash
iostat
```


Check running processes:

```bash
htop
```

Or:

```bash
top
```

Check processer being run by USER:

```bash
ps -u USER
```

Kill process by PID:

```bash
kill PID
```

Kill all processes being run by USER (including SSH session):

```bash
pkill -u USER
```

Run script that ignores hangup signal (on the background so that it does not require permanent SSH connection):

```bash
nohup python scriptName.py OPT1 OPT2 &
```

<hr>

## Backup to google drive

To backup datasets to the shared drive, first follow these instructions: https://rclone.org/drive/ (use `serverBackup` for the drive name, preferably). Then, simply run:

```bash
rclone copy FILENAME.tar.gz serverBackup:/PATH_TO_FILE --transfers=10 --checkers=10 --fast-list --drive-chunk-size=256M --verbose 
```

Tar file/folder:

```bash
tar -czvf TAR_FILENAME.tar.gz FOLDER_OR_FILE_PATH
tar -cjf ANALYZED.tar.bz2 ./ANALYZED
```

Untar file/folder:

```bash
tar -C OUTPUT_PATH -zxvf FILENAME.tar.gz
```

Tar folder to *BZ2*:

```bash
tar c ./FOLDER | lbzip2 -n CORES_NUMBER > FOLDER.tar.bz2
```

Tar folders in current directory to separate *BZ2* files:

```bash
for dir in */; do tar c "$dir" | lbzip2 -n CORES_NUMBER > "${dir%/}".tar.bz2; done
```

Batch upload files in current directory to the server:

```bash
for f in ./*.bz2; do  rclone copy  $f serverBackup:/ --transfers=10 --checkers=10 --fast-list --drive-chunk-size=256M --verbose; done
```
