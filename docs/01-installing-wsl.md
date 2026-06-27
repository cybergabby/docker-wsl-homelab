# WSL2 + Docker Desktop Setup on Windows 10

## Overview

This project documents the process of setting up a Linux development environment using **Windows Subsystem for Linux (WSL2)** and **Docker Desktop** on Windows 10.

Rather than running Kali Linux inside a virtual machine, I migrated my workflow to WSL2 to reduce resource consumption while still having access to a full Linux terminal integrated with Windows.

During the setup, I encountered multiple issues ranging from WSL installation failures to Docker daemon permissions. This document captures every step, the commands used, the errors encountered, and how each issue was resolved.

---

# Environment

| Component | Version |
|-----------|----------|
| Host OS | Windows 10 Pro |
| WSL Version | WSL2 |
| Linux Distribution | Ubuntu |
| Docker | Docker Desktop |
| Terminal | Windows Terminal |
| Shell | Bash |

---

# Why WSL2?

WSL2 provides a lightweight Linux environment that runs directly on Windows without requiring a full virtual machine.

Benefits include:

- Lower RAM usage
- Faster startup
- Direct access to Windows files
- Native Linux terminal
- Seamless Docker integration
- Better developer experience

---

# Step 1 — Installing WSL

Open **Command Prompt as Administrator**

```cmd
wsl --install
```

Initially the installation failed with:

```
Installing: Windows Subsystem for Linux

Catastrophic failure
```

---

## Diagnosis

Checking WSL status showed:

```cmd
wsl --status
```

Output

```
This application requires the Windows Subsystem for Linux Optional Component.

Error code:
WSL_E_WSL_OPTIONAL_COMPONENT_REQUIRED
```

Meaning:

The required Windows feature had not yet been enabled.

---

## Fix

Enable the required Windows features.

```
Windows Subsystem for Linux

Virtual Machine Platform
```

Restart Windows.

After rebooting:

```cmd
wsl
```

Ubuntu launched successfully.

---

# Step 2 — Verify Linux

Inside Ubuntu:

```bash
pwd

whoami

uname -a

ls
```

Example output

```
gabbytech

Linux DESKTOP-XXXX

Ubuntu
```

---

# Step 3 — Update Packages

```bash
sudo apt update

sudo apt upgrade
```

---

# Step 4 — Installing Docker Desktop

Docker Desktop was installed on Windows.

Initially WSL could not detect Docker.

Running

```bash
docker
```

returned

```
The command 'docker' could not be found in this WSL distro.
```

---

## Cause

Docker Desktop had not been integrated with Ubuntu.

---

## Fix

Inside Docker Desktop

```
Settings

↓

Resources

↓

WSL Integration

↓

Enable Ubuntu
```

Restart Docker Desktop.

Now Docker became available.

---

# Step 5 — Docker Permission Error

Running

```bash
docker build -t welcome-to-docker .
```

produced

```
permission denied while trying to connect to the Docker daemon socket
```

---

## Investigation

Checking Docker socket

```bash
ls -l /var/run/docker.sock
```

Output

```
srw-rw---- root docker
```

Checking user groups

```bash
groups
```

Output

```
gabbytech adm sudo users
```

The **docker** group was missing.

---

## Fix

Add the current user to the Docker group.

```bash
sudo usermod -aG docker $USER
```

Restart WSL.

From Windows

```cmd
wsl --shutdown
```

Open Ubuntu again.

Verify

```bash
groups
```

Output

```
gabbytech adm sudo users docker
```

---

# Step 6 — Building the First Docker Image

Navigate into the project.

```bash
cd ~/welcome-to-docker
```

Build the image.

```bash
docker build -t welcome-to-docker .
```

Docker successfully downloaded:

- base image
- dependencies
- build layers

and created the image.

---

# Verify Images

```bash
docker images
```

Example

```
REPOSITORY

welcome-to-docker

TAG

latest
```

---

# Run Container

```bash
docker run welcome-to-docker
```

or

```bash
docker run -p 8080:8080 welcome-to-docker
```

depending on the application.

---

# Commands Used

```bash
wsl --install

wsl --status

sudo apt update

sudo apt upgrade

docker

groups

ls -l /var/run/docker.sock

sudo usermod -aG docker $USER

docker build -t welcome-to-docker .

docker images

docker run welcome-to-docker
```

---

# Errors Encountered

### WSL Installation

```
Catastrophic failure
```

Resolution:

Enabled required Windows features and rebooted.

---

### Missing WSL Component

```
WSL_E_WSL_OPTIONAL_COMPONENT_REQUIRED
```

Resolution:

Enabled Windows Subsystem for Linux.

---

### Docker Not Found

```
docker: command not found
```

Resolution:

Enabled Docker Desktop WSL Integration.

---

### Permission Denied

```
permission denied while trying to connect to Docker daemon
```

Resolution:

Added user to Docker group.

---

# Lessons Learned

- WSL2 provides a lightweight Linux environment without the overhead of a virtual machine.
- Docker Desktop requires explicit WSL integration.
- Docker permissions are controlled through the **docker** group.
- Linux troubleshooting often starts with checking permissions, installed packages, and user groups.
- Understanding Linux administration is essential for DevOps, cloud engineering, and application security.

---

# Skills Demonstrated

- Linux Administration
- Windows Subsystem for Linux (WSL2)
- Docker Desktop
- Docker CLI
- Linux User Management
- Permission Troubleshooting
- Docker Image Building
- Windows/Linux Integration
- DevOps Fundamentals
