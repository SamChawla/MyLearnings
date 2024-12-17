# Docker

- [Docker](#docker)
  - [Things you should know (Helpful but not necessary)](#things-you-should-know-helpful-but-not-necessary)
  - [What is Docker?](#what-is-docker)
  - [Need for Docker](#need-for-docker)
  - [What Docker Does](#what-docker-does)
  - [What are containers?](#what-are-containers)
  - [Containers vs. Virtual Machines](#containers-vs-virtual-machines)
  - [Useful Commands](#useful-commands)
    - [Check if docker is installed properly](#check-if-docker-is-installed-properly)
    - [Check docker images available](#check-docker-images-available)
    - [Running Docker](#running-docker)
    - [Terminal Interactive run](#terminal-interactive-run)
    - [Check Running Dockers](#check-running-dockers)
    - [Creating an image from another image](#creating-an-image-from-another-image)
    - [Attach detached container](#attach-detached-container)
    - [Check docker logs](#check-docker-logs)
    - [Killing and removing docker](#killing-and-removing-docker)
    - [Networks in Docker](#networks-in-docker)
    - [Resource Constraints](#resource-constraints)
  - [Docker Compose](#docker-compose)
  - [Docker Swarn](#docker-swarn)
  - [Docker v/s Kubernetes](#docker-vs-kubernetes)

## Things you should know (Helpful but not necessary)

- Exposure to command line environment.
- Basic Networking Knowledge.
- Bash and Linux scripting experience

__Docker containers are sealed, self-contained units of software that have everything needed to run a service.__

## What is Docker?

## Need for Docker

- Compatibility/Dependency
- Long setup time
- Different Dev/Test/Prod environments

Matrix from Hell: so what is the matrix from hell? put simply, it is the challenge of packaging any application, regardless of language/frameworks/dependencies, so that it can run on any cloud, regardless of operating systems/hardware/infrastructure.

docker solved for the matrix from hell by decoupling the application from the underlying operating system and hardware. it did this by packaging all dependencies inside docker containers, including the os. this makes docker containers "portable", i.e. they can run on any cloud or machine without the dreaded "it works on this machine" problems. this is the single biggest reason docker is considered the hottest new technology of the last decade.

## What Docker Does

- Carves up a computer into sealed containers that run your code.
- Gets the code to and from your computers.
- Builds these containers for you.
- Is a social platform for you to find and share containers, which are different from virtual machines.

## What are containers?

- It is a self-contained sealed unit of software.
- Contains everything required to run the code.
- Includes batteries and OS.
- __A container includes Code, Configs, Processes, Networking, Dependencies, Minimal Operating System__.

## Containers vs. Virtual Machines


## Useful Commands

### Check if docker is installed properly

```bash
$ docker
```

### Check docker images available

```bash
$ docker images
```

### Running Docker

```bash
$ docker run <image-name> 
e.g docker run hello-world
```

### Terminal Interactive run

```bash
$ docker run -ti --name <image-name> ubuntu:latest bash 
$ docker run -d -ti --name <image-name> ubuntu:latest bash (Detach container)
```

### Check Running Dockers

```bash
$ docker ps
$ docker ps -a (For containers including the stopped ones)
```

### Creating an image from another image

```bash
$ docker commit <imageID> (Returns sha256 code)
$ docker tag <sha256 code> <new-image-name>
```
or
```bash
$ docker commit <imageID> <new-image-ID>
```

### Attach detached container

```bash
$ docker attach <ImageID>
```

### Check docker logs

```bash
$ docker logs <container-name>
```

### Killing and removing docker

```bash
$ docker kill <container-name>
$ docker rm <container-name>

```

### Networks in Docker

### Resource Constraints

```bash
$ docker run --memory <maximum-allowed-memory> <image-name> command
```

## Docker Compose

## Docker Swarn

## Docker v/s Kubernetes