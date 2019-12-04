# Server-Related

SSH into the server:

```bash
ssh USERNAME@marshall-lab-cal.berkeley.edu
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

Tar file/folder:

```bash
tar -czvf TAR_FILENAME.tar.gz FOLDER_OR_FILE_PATH
```

Untar file/folder:

```bash
tar -C OUTPUT_PATH -zxvf FILENAME.tar.gz
```

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

Deleting folder recursively (DESTRUCTIVE):

```bash
rm -R FOLDER_PATH
```

Update [MoNeT](https://pypi.org/project/MoNeT-MGDrivE/) in the server:

```bash
pip3 install --upgrade MoNeT_MGDrivE
```
