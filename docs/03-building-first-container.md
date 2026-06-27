# Building My First Docker Container

## Objective

The goal of this project was to build a Docker image from a Dockerfile and run it as a container.
<img width="1366" height="729" alt="docker2" src="https://github.com/user-attachments/assets/076040e5-3f90-4faa-b8f0-93e52c782435" />

---

# Project Structure

```
welcome-to-docker/

├── Dockerfile

├── package.json

├── src/

└── README.md
```

---

# Build the Image

```bash
docker build -t welcome-to-docker .
```

Explanation

- docker build → Builds an image
- -t → Assigns a tag
- welcome-to-docker → Image name
- . → Current directory

---

# Verify the Image

```bash
docker images
```

---

# Run the Container

```bash
docker run welcome-to-docker
```

or

```bash
docker run -p 8080:8080 welcome-to-docker
```

The -p flag maps the container port to the host machine.

---

# Verify Running Containers

```bash
docker ps
```

---

# Stop Container

```bash
docker stop CONTAINER_ID
```

---

# Remove Container

```bash
docker rm CONTAINER_ID
```

---

# Skills Learned

- Dockerfile
- Image Building
- Port Mapping
- Running Containers
- Docker CLI
