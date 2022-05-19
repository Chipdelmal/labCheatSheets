# Docker

Version:

```bash
docker --version
```

## Manipulating Images and Containers

List images:

```bash
docker image ls
```

List all containers:

```bash
docker container ls --all
```

List volumes:

```bash
docker volume ls
```

Delete all images:

```bash
docker rmi -f $(docker images -q)
```

Delete all containers:

```bash
docker rm $(docker ps -a -q)
```

## Building Images (Dockerfile in current directory)

Create image:

```bash
docker build --tag=NAME .
```

Build image with tagname:

```bash
docker build -t IMG_NAME:TAG_NAME .
```

Pushing image:

```bash
docker push IMG_NAME:TAG_NAME
```

## Running Containers

Running container in interactive bash mode:

```bash
docker run -it name:tag bash
```

Running container with mounted directory:

```bash
docker run -v SRC_HOST:DST_DKR -it mgsurve:latest bash
```

Running container with mounted directory (relative to location):

```bash
docker run -v "$(pwd)"/SRC_HOST:DST_DKR -it mgsurve:latest bash
```
