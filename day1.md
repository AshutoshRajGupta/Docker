# 🐳 Docker Basics – Quick Revision Sheet

---

## 1️⃣ Why Docker is Needed

**Problem:**
“It works on my machine” issue due to different environments.

**Solution (Docker):**

* Packages app + dependencies + runtime
* Runs consistently everywhere
* Faster development & deployment
* Lightweight compared to VMs

**Interview Line:**

> Docker ensures application consistency across environments by packaging everything into containers.

---

## 2️⃣ What is Docker?

**Definition:**
Docker is an **open-source containerization platform** used to build, ship, and run applications in containers.

**Key Points:**

* Uses host OS kernel
* Fast startup
* Portable & efficient

**Interview Line:**

> Docker is a containerization platform that enables consistent and portable application deployment.

---

## 3️⃣ What is a Docker Image?

**Definition:**
A Docker image is a **read-only blueprint** used to create containers.

**Contains:**

* App source code
* Runtime
* Dependencies
* Configurations

**Characteristics:**

* Immutable
* Built using Dockerfile
* One image → many containers

**Analogy:**
Blueprint / Recipe / Class

**Interview Line:**

> A Docker image is a read-only template that contains everything needed to run an application.

---

## 4️⃣ What is a Docker Container?

**Definition:**
A Docker container is a  **running instance of a Docker image** .

**Key Points:**

* Uses image layers
* Has its own writable layer
* Isolated from other containers
* Starts & stops quickly

**Analogy:**
House built from blueprint / Object from class

**Interview Line:**

> A Docker container is a lightweight, isolated runtime environment created from a Docker image.

---

## 5️⃣ Image vs Container (Deep Understanding)

| Feature            | Docker Image | Docker Container |
| ------------------ | ------------ | ---------------- |
| Nature             | Static       | Dynamic          |
| State              | Read-only    | Read + Write     |
| Purpose            | Blueprint    | Running app      |
| Created By         | Dockerfile   | docker run       |
| Lifecycle          | Long-lived   | Short-lived      |
| Multiple Instances | ❌           | ✅               |

**Golden Line:**

> Image is to container what  **class is to object** .

---

## 6️⃣ Dockerfile

**Definition:**
A Dockerfile is a **text file with instructions** to build a Docker image.

**Common Instructions:**

* `FROM` – Base image
* `WORKDIR` – Working directory
* `COPY` – Copy files
* `RUN` – Execute commands
* `CMD` – Start application

**Purpose:**

* Automates image creation
* Ensures reproducible builds

**Interview Line:**

> A Dockerfile defines how a Docker image is built using step-by-step instructions.

---

## 7️⃣ Docker Layers & Caching

**Concept:**

* Each Dockerfile instruction creates a **layer**
* Docker reuses unchanged layers (cache)
* Cache works **top to bottom**

**Best Practice:**

* Copy dependency files first
* Install dependencies before copying full code

**Why Important:**

* Faster builds
* Efficient CI/CD
* Smaller images

**Interview Line:**

> Docker images are built in layers, and caching helps reuse unchanged layers to optimize build time.

---

## 8️⃣ What Does “Isolated” Mean?

**Isolation Means:**

* Containers run independently
* No access to other containers’ processes or data
* Crash in one container doesn’t affect others

**How Docker Achieves It:**

* Linux namespaces
* cgroups (resource limits)

**Interview Line:**

> Isolation ensures containers run independently with separate processes, networks, and file systems.

---

## 9️⃣ Docker Run Command (Clarification)

**Command:**

```bash
docker run -it image-name
```

**What Happens:**

* Creates a container from the image
* Assigns a container ID
* Starts the container
* `-it` allows interactive terminal access

✅ Container is created and runs with its own ID
❌ You are not inside it unless `-it` or `docker exec` is used

---

## 🔟 One-Page Docker Flow (Mental Model)

```
Dockerfile → Docker Image → Docker Container → Running App
```

---
