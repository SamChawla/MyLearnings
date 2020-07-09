# Things you should know (Helpful but not necessary)

- Exposure to command line environment.
- Basic Networking Knowledge.
- Bash and Linux scripting experience 

__Docker containers are sealed, self-contained units of software that have everything needed to run a service.__

## What Docker Does

- Carves up a computer into sealed containers that run your code.
- Gets the code to and from your computers.
- Builds these containers for you.
- Is a social platform for you to find and share containers, which are different from virtual machines.

## What is a container?

- It is a self-contained sealed unit of software.
- Contains everything required to run the code.
- Includes batteries and OS.
- __A container includes Code, Configs, Processes, Networking, Dependencies, Minimal Operating System__.

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

### Resource Constraints

```bash
$ docker run --memory <maximum-allowed-memory> <image-name> command
```