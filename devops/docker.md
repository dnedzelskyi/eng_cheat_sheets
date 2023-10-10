[Home](../index.md) > DevOps > [Docker](./docker.md)

# DevOps | Docker

## Basic Commands

List Containers / Images.

```text
# List all Containers.
docker ps -a

# List all Images.
docker images -a
docker image ls
```

Working with Images.

```text
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

```text
# Just create.
docker create -it <image>

# Create, start and attach.
docker run -it <image>

# Create, start and detach immediately.
docker run -itd <image>

# Create with name, start, attach and remove after detachment.
docker run -it --rm --name <container> <image>
```

Start / Unpause Containers.

```text
# Start in the background.
docker start <container>
docker restart <container>

# Start and attach.
docker start -ia <container>

# Unpause Container.
docker unpause <container>
```

Stop / Pause / Restart Containers.

```text
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

```text
# Remove Container that is not running.
docker rm <container>
docker remove <container>

# Force stop and remove.
docker remove -f <container>
```

Attach Containers.

```text
# Just attach.
docker attach <container>

# Attach and execute shell (bash as ex.) on running Container.
docker exec -it <container> bash
```

Check where the hell are you at and what's going on.

```text
# Current user
whoami

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

## Docker File

Docker file basics.

```text
FROM <image>

USER <user>

RUN <command>

WORKDIR <path>

COPY [--chown=<user>:<group>|--from=<stage>] <host/stage_path> <container_path>

EXPOSE <ports>

CMD ["cmd 1", "cmd 2", ...]
```

### Commands

```text
# Build Image from dockerfile.
docker build -t <image> .

# Runs new container with exposed port to host.
docker run -dit -p <container_port>:<host_port> <image>

# Runs new container with exposed port to host and removes it after stop.
docker run -it -p <container_port>:<host_port> --name <container> --rm <image>

# Runs new container and expose all ports (see EXPOSE in docker file).
docker run -dit -P --name <container> <image>
```
