## 🧱 Docker Image Layers

### 🔹 What are Docker Image Layers?

- Docker images are built using **layers**
- Each instruction in a `Dockerfile` creates one layer
- Layers are **read-only** and **cached**
- Multiple images can **share layers**

---

### 🔹 Base Layer

- The **first layer** of an image
- Defined using `FROM`
- Provides OS and runtime

Example:

```dockerfile
FROM node:18
```

👉 This becomes the **base layer**

---

### 🔹 Container Layer (Writable Layer)

- Created when a container runs
- Sits on **top of image layers**
- Stores runtime changes, logs, temp files
- Deleted when container is removed

Layer view:

```
Writable Container Layer
-----------------------
App Code Layer
Dependencies Layer
Runtime Layer
Base OS Layer
```

---

### 🔹 Why Layers Matter

- Faster builds (caching)
- Smaller images
- Efficient CI/CD

---

## 🔌 Port Binding (Port Mapping)

### 🔹 What is Port Binding?

Port binding maps:

- **Host machine port**
- To a **container’s internal port**

This allows external access to container applications.

---

### 🔹 Command for Port Binding

```bash
docker run -p hostPort:containerPort image-name
```

Example:

```bash
docker run -p 8080:3000 my-node-app
```

Meaning:

- App runs on port `3000` inside container
- Accessible on `localhost:8080`

---

### 🔹 EXPOSE vs -p

- `EXPOSE` → documentation only
- `-p` → actually binds the port

---

## 🛠️ Docker Troubleshooting Commands

### 🔹 View Container Logs

Shows logs of a container.

```bash
docker logs container-id-or-name
```

Follow logs in real-time:

```bash
docker logs -f container-name
```

---

### 🔹 Inspect Container Details

Shows configuration and runtime details.

```bash
docker inspect container-name
```

---

### 🔹 Check Resource Usage

Displays CPU and memory usage.

```bash
docker stats
```

---

## 🧑‍💻 Docker exec Command

### 🔹 What is `docker exec`?

Used to **run commands inside a running container** .

---

### 🔹 Go Inside a Running Container

```bash
docker exec -it container-name bash
```

If bash is not available:

```bash
docker exec -it container-name sh
```

---

### 🔹 When to Use exec

- Debug running containers
- Check files
- Inspect logs manually
- Run database or shell commands

---

## 🧠 Common Docker Debug Flow

```bash
docker ps
docker logs container-name
docker exec -it container-name bash
```

---

## ⚖️ Docker vs Virtual Machine

### 🔹 Key Differences (Points)

| Feature        | Docker         | Virtual Machine |
| -------------- | -------------- | --------------- |
| OS             | Shared host OS | Separate OS     |
| Startup Time   | Seconds        | Minutes         |
| Resource Usage | Low            | High            |
| Image Size     | MBs            | GBs             |
| Isolation      | Process-level  | Hardware-level  |
| Performance    | Near native    | Slower          |
| Portability    | Very high      | Medium          |

---

### 🔹 Simple Example

- **Virtual Machine** : Separate house for each app
- **Docker** : Separate rooms in the same house
