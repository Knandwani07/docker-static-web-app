# ⚙️ Execution Workflow

## 🔄 Workflow Diagram

```text
+--------------------+
|     Developer      |
+--------------------+
          │
          ▼
+------------------------------+
| index.html + Dockerfile      |
+------------------------------+
          │
          │ docker build
          ▼
+------------------------------+
| Docker Image (my-web-app)    |
+------------------------------+
          │
          │ docker run
          ▼
+------------------------------+
| Docker Container             |
| • Nginx                      |
| • HTML Application           |
+------------------------------+
          │
          │ Port Mapping
          │ 8080 → 80
          ▼
+------------------------------+
| http://localhost:8080        |
+------------------------------+
          │
          ▼
+------------------------------+
|        Web Browser           |
+------------------------------+
```

---

## Workflow

1. The developer creates the **HTML application** and a **Dockerfile** that defines how the Docker image will be built.
2. Docker builds a custom **Docker image** containing the application and the Nginx web server.
3. A **Docker container** is created from the image using the `docker run` command.
4. Nginx starts automatically inside the container and serves the HTML application.
5. Docker maps **port 8080** on the host machine to **port 80** inside the container using port mapping.
6. The user accesses the application by visiting **http://localhost:8080** in a web browser.
7. Docker forwards the request to the Nginx server running inside the container, which serves the HTML page back to the browser.

## Container Management

- Use `docker ps` to verify the container is running.
- Use `docker logs` to inspect the container logs.
- Use `docker exec -it web-container bash` to access the container shell.
- Use `docker stop`, `docker start`, and `docker rm` to manage the container lifecycle.

## Port Mapping

- The `-p 8080:80` option maps **port 8080** on the host machine to **port 80** inside the container, allowing the application to be accessed through a web browser.
