
## 2.2 Lab – Introduction to Docker (GitHub Codespaces Version)

### **Introduction**

Welcome to the "Introduction to Docker" hands-on lab using **GitHub Codespaces**. In this lab, you’ll interact with Docker through the integrated terminal in Codespaces. You’ll pull images, run containers, view logs, and explore running containers — all in the cloud with no setup required on your local machine.

---

### **Objectives**

By the end of this lab, you will be able to:

* Pull Docker images from Docker Hub.
* Run and manage Docker containers.
* View container logs and explore a container’s shell.
* Use GitHub Codespaces to run Docker commands in the cloud.

---

### **Lab Steps**

---

### **Step 1: Launch GitHub Codespaces**

1. Go to the repository configured for this lab (e.g., `intro-to-docker-lab`).
2. Click the green **“Code”** button, then choose **“Codespaces” > “Create codespace on main”**.
3. Wait for the Codespace to open in your browser.

> 🔧 Docker is preconfigured in the dev container for this lab using Docker-in-Docker (dind).

4. Open a terminal: select **Terminal > New Terminal** or press **Ctrl + \`**.

---

### **Step 2: Verify Docker Is Working**

Run the following command:

```bash
docker --version
```

You should see output like:

```
Docker version 24.0.x, build abc123
```

---

### **Step 3: Pull a Docker Image**

Pull the official `hello-world` image from Docker Hub:

```bash
docker pull hello-world
```

Then list your local images:

```bash
docker images
```

You should see `hello-world` listed.

---

### **Step 4: Run the Hello World Container**

Run the container:

```bash
docker run hello-world
```

This runs the image and outputs a confirmation message from Docker.

---

### **Step 5: Manage Containers**

Check for running containers:

```bash
docker ps
```

Since the `hello-world` container exits immediately, list all containers (including stopped):

```bash
docker ps -a
```

Stop and remove any containers if needed (replace `CONTAINER_ID`):

```bash
docker stop CONTAINER_ID
docker rm CONTAINER_ID
```

---

### **Step 6: Run and Inspect an Nginx Container**

Run a background Nginx container:

```bash
docker run -d --name my-nginx nginx
```

Check logs:

```bash
docker logs my-nginx
```

Access the shell inside the running container:

```bash
docker exec -it my-nginx /bin/bash
```

Explore, then exit with:

```bash
exit
```

---

### **Step 7: Cleanup**

Stop and remove the running container:

```bash
docker stop my-nginx
docker rm my-nginx
```

Verify cleanup:

```bash
docker ps
```

You should see no containers running:

```
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

---

### **Summary**

In this GitHub Codespaces-based Docker lab, you:

* Verified your Docker environment in the cloud
* Pulled and ran a simple container
* Explored container logs and terminal access
* Managed and cleaned up containers

These skills form the foundation for building and managing containerized applications using Docker.
