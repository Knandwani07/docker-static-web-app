# Deployment Guide

This guide explains how to build, run, verify, and clean up the Docker Static Web App on your local machine.

---

# 📋 Prerequisites

Before you begin, ensure you have:

* Docker Desktop (Windows/macOS) or Docker Engine (Linux) installed
* Docker running successfully
* Basic familiarity with the command line

Verify the installation:

```bash
docker --version
docker ps
```

---

# 📂 Clone the Repository

Clone the project and navigate into the project directory.

```bash
git clone https://github.com/Knandwani07/docker-static-web-app.git
cd docker-static-web-app
```

---

# 🏗️ Build the Docker Image

Build the Docker image using the Dockerfile.

```bash
docker build -t my-web-app .
```

Verify the image was created successfully.

```bash
docker images
```

Expected output:

```text
REPOSITORY     TAG       IMAGE ID
my-web-app     latest    xxxxxxxxxxxx
```

---

# ▶️ Run the Container

Create and start the container.

```bash
docker run -d -p 8080:80 --name web-container my-web-app
```

Verify the container is running.

```bash
docker ps
```

---

# 🌐 Access the Application

Open your browser and navigate to:

```text
http://localhost:8080
```

The HTML page should load successfully.

---

# 📜 View Container Logs

View the Nginx logs.

```bash
docker logs web-container
```

---

# 🖥️ Access the Container

Open an interactive shell.

```bash
docker exec -it web-container bash
```

Navigate to the web root.

```bash
cd /usr/share/nginx/html
ls
```

Exit the container.

```bash
exit
```

---

# ⏹️ Stop the Container

Stop the running container.

```bash
docker stop web-container
```

Restart it when needed.

```bash
docker start web-container
```


---

# ✅ Deployment Verification Checklist

* Docker is installed and running.
* Docker image builds successfully.
* Container starts without errors.
* Application is accessible at **http://localhost:8080**.
* Nginx logs show successful requests.
* Container can be stopped, restarted, and removed successfully.

---

# 🎉 Deployment Complete

Your Docker Static Web App is now successfully deployed and running in a Docker container. You have completed the complete deployment workflow, including image creation, container execution, verification, management, and cleanup.
