# Docker Static Web App

A beginner-friendly Docker project that demonstrates the complete containerization workflow by packaging a simple HTML web application with Docker and Nginx. This project covers the fundamentals of building Docker images, running containers, exposing applications through port mapping, and managing the container lifecycle.

---

## 🚀 Features

* Containerize a static HTML website using Docker
* Build a custom Docker image with a Dockerfile
* Serve the application using Nginx
* Access the application through port mapping
* Inspect logs and interact with the running container
* Practice the complete Docker container lifecycle

---

## 🛠️ Technologies Used

* Docker
* Dockerfile
* Nginx
* HTML

---

## 📂 Project Structure

```text
docker-static-web-app/
├── Dockerfile
├── index.html
└── README.md
```

---

## ⚡ Getting Started

### Clone the repository

```bash
git clone https://github.com/Knandwani07/docker-static-web-app.git
cd docker-static-web-app
```

### Build the Docker image

```bash
docker build -t my-web-app .
```

### Run the container

```bash
docker run -d -p 8080:80 --name web-container my-web-app
```

### Access the application

Open your browser and visit:

```text
http://localhost:8080
```

---

## 📋 Useful Docker Commands

### View running containers

```bash
docker ps
```

### View container logs

```bash
docker logs web-container
```

### Open a shell inside the container

```bash
docker exec -it web-container bash
```

### Stop the container

```bash
docker stop web-container
```

### Start the container

```bash
docker start web-container
```

### Remove the container

```bash
docker rm web-container
```

### Remove the image

```bash
docker rmi my-web-app
```

---

## 🎯 Learning Outcomes

* Understand the difference between Docker images and containers
* Build Docker images using a Dockerfile
* Run and manage Docker containers
* Expose applications using port mapping
* Inspect logs and troubleshoot running containers
* Practice the Docker container lifecycle

---

## 🤝 Connect with Me

* **LinkedIn:** https://www.linkedin.com/in/khushi-nandwani/
* **GitHub:** https://github.com/Knandwani07
