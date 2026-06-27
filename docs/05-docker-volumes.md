# Docker Volumes

## Overview

Containers are ephemeral.

When a container is deleted, its data is lost.

Volumes allow data persistence.

---

# Create Volume

```bash
docker volume create my-volume
```

---

# List Volumes

```bash
docker volume ls
```

---

# Mount Volume

```bash
docker run -v my-volume:/data nginx
```

---

# Inspect Volume

```bash
docker volume inspect my-volume
```

---

# Remove Volume

```bash
docker volume rm my-volume
```

---

# Skills Learned

- Persistent Storage
- Docker Volumes
- Volume Mounting
