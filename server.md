# Server-Related

SSH into the server:

```bash
ssh USERNAME@marshall-lab-cal.berkeley.edu
```

<hr>

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

Tar file/folder:

```bash
tar -czvf TAR_FILENAME.tar.gz FOLDER_OR_FILE_PATH
```

Untar file/folder:

```bash
tar -C OUTPUT_PATH -zxvf FILENAME.tar.gz
```

<hr>

Check disk usage

```bash
ncdu
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

<hr>

Run script that ignores hangup signal (on the background so that it does not require permanent SSH connection):

```bash
nohup python scriptName.py OPT1 OPT2 &
```

Start *tmux* session:

```bash
tmux
```

List active *tmux* sessions:

```bash
tmux ls
```

Attach to active *tmux* session by ID:

```bash
tmux attach -t ID
```

Detach active *tmux* session (keyboard):

```
CTRL + B
then d
```

<hr>

Delete folder recursively (DESTRUCTIVE):

```bash
rm -R FOLDER_PATH
```


