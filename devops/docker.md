[Home](../index.md) > DevOps > [Docker](./docker.md)

# DevOps | Docker

## Basic Commands

List container / images.

```
# List all containers.
docker ps -a

# List all images.
docker images -a
docker image ls
```

Pull images from DockerHub.

```
docker pull <image_name[:tag|@digest]>
```

Create containers.

```
# Just create.
docker create -it <image>

# Create, start and attach.
docker run -it <image>

# Create, start and detach immediately.
docker run -itd <image>

# Create with name, start, attach and remove after detachment.
docker run -it --name <container_name> --rm <image>
```

Start containers.

```
# Start in the background.
docker start <container>

# Start and attach.
docker start -ia <container>
```

Stop containers.

```
# Gracefully stop running container.
docker stop <container>

# Forcefully stop unresponsive container.
docker kill <container>
```

Delete containers.

```
# Remove container that is not running.
docker remove <container>

# Force stop and remove.
docker remove -f <container>

```

Check where the hell are you at.

```
cat /etc/issue
```
