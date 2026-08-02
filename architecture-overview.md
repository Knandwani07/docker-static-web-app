# 🏛️ Architecture Overview
<img width="1456" height="819" alt="image" src="https://github.com/user-attachments/assets/9bcacc45-10b0-4a98-8201-ab8c49c63910" />


This project follows a simple single-container architecture where a static HTML application is packaged into a Docker image using a Dockerfile and served by an Nginx web server running inside a Docker container. Docker handles container creation, while port mapping exposes the application to the host machine, allowing users to access it through a web browser.

---

# 🏗️ Architecture Components

### **Developer Environment**
Contains the project files (`index.html` and `Dockerfile`) used to build the Docker image.

### **Docker Image (`my-web-app:latest`)**
A reusable image built from the Dockerfile. It packages the Nginx web server together with the custom HTML application.

### **Host Machine**
Runs Docker Engine, which manages Docker images, containers, and port mapping between the host and the container.

### **Docker Container (`web-container`)**
A running instance of the Docker image. It hosts the Nginx web server and serves the application on port **80** inside the container.

### **Port Mapping (`8080 → 80`)**
Maps **port 8080** on the host machine to **port 80** inside the container, allowing external access to the application.

### **Browser / End User**
Accesses the application by visiting **http://localhost:8080**, where Docker forwards the request to the Nginx server running inside the container.

---

# 🔄 Flow

1. The developer creates the application files (`index.html` and `Dockerfile`).
2. Docker builds a custom image using the Dockerfile.
3. A Docker container is created and started from the image.
4. Nginx serves the HTML application inside the container.
5. Docker maps **port 8080** on the host machine to **port 80** inside the container.
6. The user accesses the application through **http://localhost:8080**.
7. Docker forwards the request to the container, and Nginx returns the web page.

---

# 🔐 Security Highlights

- The application runs inside an **isolated Docker container**, reducing its impact on the host system.
- Only **port 8080** is exposed on the host, while the application continues listening on **port 80** inside the container.
- The container uses the official **Nginx** base image, providing a trusted and lightweight web server.
- The host and container communicate through Docker's **port mapping**, keeping internal container networking isolated from the host.
