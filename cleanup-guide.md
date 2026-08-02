# 🧹 Cleanup Guide

This guide explains how to remove all Docker resources created during this project. Performing cleanup helps free system resources and keeps your Docker environment organized.

---

# 📋 Cleanup Order

Remove the resources in the following order:

1. Stop the running container
2. Remove the container
3. Remove the Docker image
4. Verify all resources have been deleted

---

# 1️⃣ Stop the Container

If the container is still running, stop it before attempting to remove it.

```bash
docker stop web-container
```

Verify that the container has stopped.

```bash
docker ps
```

---

# 2️⃣ Remove the Container

Delete the stopped container.

```bash
docker rm web-container
```

Verify that the container has been removed.

```bash
docker ps -a
```

The `web-container` should no longer appear in the list.

---

# 3️⃣ Remove the Docker Image

Delete the Docker image created during this project.

```bash
docker rmi my-web-app
```

Verify that the image has been removed.

```bash
docker images
```

The `my-web-app` image should no longer appear in the output.

---

# 4️⃣ (Optional) Remove Unused Docker Resources

To remove unused containers, networks, dangling images, and build cache:

```bash
docker system prune
```

To remove all unused images as well:

```bash
docker system prune -a
```

> **Note:** This command removes all unused Docker resources from your local machine, not just those created for this project.

---

# ✅ Verify Cleanup

Run the following commands to confirm all project resources have been removed.

```bash
docker ps -a
docker images
```

Neither **web-container** nor **my-web-app** should appear in the output.

---

# 🎉 Cleanup Complete

Your Docker environment has been successfully cleaned up. All project-specific containers and images have been removed, leaving your local Docker installation ready for future projects.
