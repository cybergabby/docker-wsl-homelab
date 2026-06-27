# Troubleshooting Log

Throughout this project I encountered several issues while setting up Docker and WSL.
<img width="1366" height="642" alt="dockererror3" src="https://github.com/user-attachments/assets/3e3deb96-b91a-48b7-b88d-ac63edc30ae7" />
<img width="1366" height="734" alt="docker4" src="https://github.com/user-attachments/assets/f3c22fbc-3811-413f-b065-6513c8bb49b5" />


---

## Issue 1

Docker command not found

```
docker: command not found
```

Cause

Docker Desktop WSL Integration was disabled.

Solution

Enable Ubuntu under

Docker Desktop

↓

Settings

↓

Resources

↓

WSL Integration

---

## Issue 2

Permission denied

```
permission denied while trying to connect to Docker daemon
```

Cause

Current user was not in the docker group.

Solution

```bash
sudo usermod -aG docker $USER
```

Restart WSL.

---

## Issue 3

Unable to locate image

```
Unable to find image
```

Cause

Docker attempted to pull an image that did not exist locally.

Resolution

Docker automatically downloaded it from Docker Hub.

---

# Lessons Learned

Most Docker issues are caused by

- Permissions
- Missing images
- Docker daemon
- WSL Integration
- Networking

Checking logs and reading error messages greatly simplifies troubleshooting.
