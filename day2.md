## 📦 Docker Image Commands

### 🔹 Pull a Docker Image

Downloads an imageAttach from Docker Hub.

```bash
docker pull image-name
```

Example:

```bash
docker pull nginx
```

---

### 🔹 Pull Image with Specific Version (Tag)

Pulls a specific version of an image.

```bash
docker pull image-name:tag
```

Example:

```bash
docker pull node:18
```

---

### 🔹 List Docker Images

Shows all Docker images available locally.

```bash
docker images
```

---

## 🚀 Docker Container Commands

### 🔹 Run a Container from an Image

Creates and starts a container from an image.

```bash
docker run image-name
```

---

### 🔹 Run Container in Interactive Mode

Starts container and opens terminal access.

```bash
docker run -it image-name
```

Example:

```bash
docker run -it ubuntu
```

---

### 🔹 Run Container with a Name

Assigns a custom name to the container.

```bash
docker run --name container-name image-name
```

Example:

```bash
docker run --name my-container ubuntu
```

---

### 🔹 Run Container in Detached Mode

Runs container in background.

```bash
docker run -d image-name
```

---

## 📋 Container Status & Management

### 🔹 List Running Containers

Shows only currently running containers.

```bash
docker ps
```

---

### 🔹 List All Containers (Running + Stopped)

Shows all containers.

```bash
docker ps -a
```

---

### 🔹 Start a Stopped Container

Starts an existing stopped container.

```bash
docker start container-id-or-name
```

---

### 🔹 Stop a Running Container

Stops a running container.

```bash
docker stop container-id-or-name
```

---

## 🧹 Cleanup Commands

### 🔹 Remove a Container

Deletes a stopped container.

```bash
docker rm container-id-or-name
```

---

### 🔹 Remove a Docker Image

Deletes a Docker image.

```bash
docker rmi image-id-or-name
```

---

## 🧠 Quick Interview Notes

- `docker run` → creates **and** starts a container
- `docker start` → starts an **existing** container
- `-it` → interactive terminal
- `-d` → detached (background) mode
- Image = blueprint
- Container = running instance
