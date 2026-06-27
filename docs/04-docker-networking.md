# Docker Networking

## Overview

Containers communicate using Docker Networks.

Each container receives its own private IP address.

Docker creates a default bridge network.

---

# View Networks

```bash
docker network ls
```

---

# Inspect Network

```bash
docker network inspect bridge
```

---

# Create Custom Network

```bash
docker network create app-network
```

---

# Run Container on Network

```bash
docker run --network app-network nginx
```

---

# Remove Network

```bash
docker network rm app-network
```

---

# Skills Learned

- Docker Networking
- Bridge Networks
- Container Communication
