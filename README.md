# Static Website CI/CD Project

## 📌 Project Overview

This project demonstrates a **fully automated CI/CD pipeline** for deploying a **static website** using **GitHub, Jenkins, Docker, Docker Compose, and DockerHub**. Whenever changes are pushed to GitHub, the Jenkins pipeline automatically builds the Docker image, pushes it to DockerHub, and deploys the updated website using Docker Compose.

---

## 🧩 Tech Stack

* **Frontend:** HTML, CSS, JavaScript (Static Website)
* **CI/CD:** Jenkins (Declarative Pipeline)
* **Containerization:** Docker, Docker Compose
* **Source Code Management:** GitHub
* **Container Registry:** DockerHub
* **Deployment Environment:** Linux / AWS EC2

---

## 📁 Project Structure

```
static-website/
│
├── index.html          # Main HTML page
├── style.css           # CSS styles
├── script.js           # JavaScript for interactivity
├── Dockerfile          # Dockerfile to build the image
├── docker-compose.yml  # Docker Compose file for deployment
└── Jenkinsfile         # Jenkins Declarative Pipeline
```

---

## 🚀 Features

* Simple static website using HTML, CSS, and JavaScript
* Fully automated CI/CD pipeline using Jenkins
* Automatic Docker image build and push to DockerHub
* Automatic deployment using Docker Compose
* Supports versioned Docker images and rolling updates

---

## 🛠️ Prerequisites

* Jenkins installed on a Linux server or EC2 instance
* Docker and Docker Compose installed
* DockerHub account (**username:** `shiv201`)
* GitHub repository:

  * [https://github.com/gawalishankar/static-website.git](https://github.com/gawalishankar/static-website.git)

---

## ⚡ Installation & Deployment

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/gawalishankar/static-website.git
cd static-website
```

---

### 2️⃣ Build Docker Image (Manual Test)

```bash
docker build -t shiv201/static-web .
```

---

### 3️⃣ Run Container Locally

```bash
docker run -d -p 8080:80 shiv201/static-web
```

Open your browser:

```
http://localhost:8080
```

---

### 4️⃣ Deploy Using Docker Compose

```bash
docker-compose up -d
```

Access the website:

```
http://<EC2-PUBLIC-IP>:8080
```

---

## 🔗 CI/CD with Jenkins

### Jenkins Setup Steps

1. Create a **Jenkins Pipeline Job**
2. Connect it to the GitHub repository
3. Use the `Jenkinsfile` present in the repository
4. Configure **DockerHub credentials** in Jenkins
5. Add a **GitHub Webhook** to trigger the pipeline on every push

---

### 🧪 Pipeline Stages

* **Checkout** code from GitHub
* **Build** Docker image
* **Push** image to DockerHub
* **Deploy** container using Docker Compose

---

## ✅ Key Outcomes

* End-to-end automated CI/CD pipeline
* Zero manual deployment effort
* Fast and reliable static website deployment
* Industry-standard DevOps workflow using Docker and Jenkins

---

✨ **Project successfully demonstrates real-world CI/CD automation for static web applications.**
