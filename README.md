# Docker & WSL2 Homelab

<img width="1073" height="732" alt="docker6" src="https://github.com/user-attachments/assets/59e96983-f857-43e5-b2c8-868adf8ccee9" />


A hands-on homelab documenting my journey of setting up Docker Desktop with Ubuntu WSL2 on Windows, troubleshooting common integration issues, and deploying my first containerized application.

This project focuses on understanding how Docker works with WSL2, resolving real-world configuration problems, and building a functional development environment for Cloud-Native Application Security.

---

## Objectives

- Install Ubuntu on WSL2
- Configure Docker Desktop with WSL Integration
- Troubleshoot Docker permission issues
- Build a Docker image
- Run a container locally
- Document common issues and solutions

---

## Environment

| Component | Version |
|-----------|----------|
| Windows | Windows 10 Pro |
| WSL | WSL2 |
| Linux | Ubuntu |
| Docker | Docker Desktop |
| Container | Node.js |

---

## Skills Demonstrated

- Windows Subsystem for Linux (WSL2)
- Linux Administration
- Docker Desktop
- Docker CLI
- Dockerfile
- Containerization
- Troubleshooting
- Linux Permissions
- Command Line

---

## Repository Structure

```
docs/
screenshots/
app/
README.md
```

---

## Topics Covered

- Installing WSL2
- Docker Desktop Installation
- WSL Integration
- Docker Groups
- Docker Socket Permissions
- Building Images
- Running Containers
- Troubleshooting

---

## Lessons Learned During this Lab SetUp

One of the biggest takeaways from this project was that Docker installation is often straightforward—but integrating Docker Desktop with WSL2 and resolving Linux permission issues requires understanding how Docker communicates with the Docker daemon through the Unix socket.

Learning how Docker uses Linux groups (`docker`) significantly improved my understanding of container environments.

---

## Screenshots

<img width="1366" height="729" alt="docker2" src="https://github.com/user-attachments/assets/556f20b9-f57b-49bf-b1bb-c5965bfa4184" />
<img width="1366" height="728" alt="Docker1" src="https://github.com/user-attachments/assets/7b4cf60c-ad06-440e-89e4-013e47e9833c" />


---

## Author

Gabriel Odusanya
Cloud & Application Security
