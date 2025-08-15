# update
Removed supervisord management for the original project. Therefore, no longer needed supervisord.conf.
Changed to managing required startup content in /home/user/start.sh.
Added path mapping; users' directories need to be mapped to the host for persistent data storage.

# Ubuntu

This project provides a custom Docker image based on Ubuntu, designed to simulate a minimal VPS environment. It includes an SSH server enabled by default, allowing users to interact with the container just like a typical remote server. This setup is ideal for testing, development, or training purposes where a lightweight and easily reproducible virtual server is needed.

## Usage

```bash
docker run -d \
  --name ubuntu \
  -p 2222:22 \
  -v /etc/ubuntu:/home/ubuntu \
  -e SSH_USER=ubuntu \
  -e SSH_PASSWORD='ubuntu!23' \
  ghcr.io/vevc/ubuntu:25.7.14
```

