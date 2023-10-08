[Home](../index.md) > DevOps > [Docker](./docker.md)

# DevOps | Docker

## Basic Commands

List Containers / Images.

```shell
# List all Containers.
docker ps -a

# List all Images.
docker images -a
docker image ls
```

Working with Images.

```shell
# Search for Image.
docker search <image>
docker search -f is-official=true <image>

# Pull Image from DockerHub.
docker pull <image[:tag|@digest]>

# View Image info.
docker inspect <image>
docker history <image>

# Remove Image.
docker rmi <image>
docker image remove <image>
```

Create Containers.

```shell
# Just create.
docker create -it <image>

# Create, start and attach.
docker run -it <image>

# Create, start and detach immediately.
docker run -itd <image>

# Create with name, start, attach and remove after detachment.
docker run -it --name <container> --rm <image>
```

Start / Unpause Containers.

```shell
# Start in the background.
docker start <container>
docker restart <container>

# Start and attach.
docker start -ia <container>

# Unpause Container.
docker unpause <container
```

Stop / Pause / Restart Containers.

```shell
# Gracefully stop running Container.
docker stop <container>

# Forcefully stop unresponsive Container.
docker kill <container>

# Put Container on hold.
docker pause <container>

# Restart Container.
docker restart <container>

# Stop all running Containers (Unix, Linux ... etc).
docker stop $(docker ps -q)

# Stop all running Containers (Win CMD).
for /f "tokens=*" %i in ('docker ps -q') do docker stop %i
```

Delete Containers.

```shell
# Remove Container that is not running.
docker rm <container>
docker remove <container>

# Force stop and remove.
docker remove -f <container>
```

Attach Containers.

```shell
# Just attach.
docker attach <container>

# Attach and execute shell (bash as ex.) on running Container.
docker exec -it <container> bash
```

Check where the hell are you at and what's going on.

```shell
# Info about OS (Linux, Unix ... etc.)
cat /etc/issue

# Info about System (Win CMD)
systeminfo

# Info about docker runtime.
docker info

# View running processes of a Container.
docker top <container>

# View Container logs with time.
docker logs -t <container>
```
