# Docker

## Terminology
- **Image**: a blueprint (like a Class)
- **Container**: an instance of image

## Create docker image

**Create a `Dockerfile`**

```bash
FROM ubuntu:20.04

COPY run-tests.sh /home/run-tests.sh 
```
Note: Copy run-tests.sh to the image under /home folder

**Structure**:
```
- Dockerfile
- run-tests.sh
```

**Build and tag locally**

```bash
docker build -t hello-world .
```
`.` indicate find Dockerfile in path `./`

**Check the docker image**

```bash
docker image ls
```

## Run a Docker image as a container

**Run a container**

```bash
docker run -i -t hello-world:latest /bin/bash
```
or
```bash
docker run -i -t image_id /bin/bash
```
Note: use `exit` to exit a container terminal.

**Check container**

Check all container
```bash
docker ps -a
```
Check running container
```bash
docker container ls
```

## Image Management
```bash
docker image ls
docker image rmi -f image_id
docker image rm REPOSITORY_name
```

## Container Management
```bash
docker container ls
docker container ls -a
docker start container_name
docker stop container_name
docker container rm container_id
```
Remove all container:
```bash
docker rm -f $(docker ps -q -a)
```

## Github Package

You can use [Githubb Package](https://docs.github.com/en/packages/learn-github-packages/introduction-to-github-packages) to host a image.
