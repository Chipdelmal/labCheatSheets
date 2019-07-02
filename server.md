# Server-Related



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
