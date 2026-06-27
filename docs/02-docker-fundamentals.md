# Docker Fundamentals

## Overview

Docker is a containerization platform that allows developers to package applications together with all their dependencies into lightweight, portable containers.

Unlike virtual machines, containers share the host operating system kernel, making them significantly faster and more efficient.

Understanding Docker is essential for DevOps, Cloud Engineering, Application Security, and modern software development.
<img width="1366" height="488" alt="containers" src="https://github.com/user-attachments/assets/2855cb7e-b425-4e0f-a480-9c0bf60edc06" />


---

# Why Containers?

Traditional application deployment often suffers from dependency conflicts.

Example:

Developer A

Python 3.12

↓

Application works

Developer B

Python 3.9

↓

Application breaks

Containers solve this by packaging:

- Application code
- Runtime
- Libraries
- Dependencies
- Configuration

into one portable image.

---

# Docker Architecture

Docker consists of several core components.

Docker Client

↓

Docker Daemon

↓

Docker Image

↓

Docker Container

The Docker Client sends commands.

The Docker Daemon builds and manages images and containers.

Images act as templates.

Containers are running instances of images.

---

# Common Docker Commands

## Check Docker Version

```bash
docker --version
```

---

## View Docker Information

```bash
docker info
```

---

## List Images

```bash
docker images
```

---

## List Running Containers

```bash
docker ps
```

---

## List All Containers

```bash
docker ps -a
```

---

## Remove Container

```bash
docker rm CONTAINER_ID
```

---

## Remove Image

```bash
docker rmi IMAGE_ID
```

---

# Image vs Container

Image

- Blueprint
- Read-only
- Can create many containers

Container

- Running instance
- Read/Write
- Executes the application

---

# Skills Learned

- Docker Architecture
- Docker CLI
- Images
- Containers
- Docker Daemon
- Docker Client
