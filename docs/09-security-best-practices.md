# Docker Security Best Practices

## Principle of Least Privilege

Avoid running containers as the root user whenever possible.

---

## Keep Images Updated

Regularly pull updated base images to receive the latest security patches.

---

## Scan Images

Use image scanning tools to identify vulnerabilities before deployment.

Example:

```bash
docker scout quickview
```

or

```bash
trivy image IMAGE_NAME
```

---

## Secrets Management

Do not hardcode:

- Passwords
- API Keys
- Tokens
- Certificates

Use environment variables or dedicated secret management solutions.

---

## Minimize Attack Surface

Use lightweight base images such as Alpine Linux where appropriate to reduce unnecessary packages.

---

## Skills Learned

- Container Security
- Secure Image Management
- Secrets Management
- Least Privilege
