# Docker Cheatsheet

Welcome to the Docker Cheatsheet! This cheat sheet provides a quick reference to essential Docker commands and their usage. Docker is a powerful platform for developing, shipping, and running applications in containers.

## Table of Contents

- [List All Available Images](#list-all-available-images)
- [Pull an Image](#pull-an-image)
- [List Running Containers](#list-running-containers)
- [List All Containers](#list-all-containers)
- [Run a Container](#run-a-container)
- [Run a Container with Options](#run-a-container-with-options)
- [Start a Container](#start-a-container)
- [Stop a Container](#stop-a-container)
- [Kill a Container](#kill-a-container)
- [Remove a Container](#remove-a-container)
- [Remove a Container (Forcefully)](#remove-a-container-forcefully)
- [Prune Images](#prune-images)
- [Prune Containers](#prune-containers)

## List all available images
```bash 
docker images
```
## Pull an image
```bash 
docker pull <image_name>:<tag>
```
Pull the latest version of an image (if the tag is not mentioned)

## List running containers
```bash 
docker ps
```
## List all containers
```bash 
docker ps -a
```
## Run a container
```bash 
docker run <image_name>
```
Create and run a container, giving it a random name

## Run a container with options
```bash
docker run -d -p <host_port>:<container_port> --rm --name <container_name> <image_name>
```
Create and run a container with the specified options:
- `-d`: Run the container in detach mode, which means the container continues running even if we kill the terminal.
- `-p <host_port>:<container_port>`: Map a port on the host to a port on the container.
- `--rm`: Automatically remove the container when it exits.
- `--name <container_name>`: Specify a custom name for the container.

## Start a container
```bash 
docker start <container_name/id>
```
## Stop a container
```bash 
docker stop <container_name/id>
```
Stop a running container with cleanup
## Kill a container
```bash 
docker kill <container_name/id>
```
Forcefully terminate a container without cleanup
## Remove a container
```bash 
docker rm <container_name/id>
```
## Remove a container forcefully
```bash 
docker rm -f <container_name/id>
```
Forcefully remove a container (even if it's not stopped)
## Prune images
```bash 
docker image prune 
```
Remove all unused images
## Prune containers
```bash 
docker container prune
```
Remove all unused containers