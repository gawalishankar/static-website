Static Website CI/CD Project
Project Overview

This project demonstrates a fully automated CI/CD pipeline for deploying a static website using GitHub, Jenkins, Docker, Docker Compose, and DockerHub.
The pipeline automatically builds, pushes, and deploys the static website container whenever changes are pushed to GitHub.

🧩 Tech Stack

Frontend: HTML, CSS, JavaScript (Static website)

CI/CD: Jenkins Declarative Pipeline

Containerization: Docker, Docker Compose

Repository: GitHub

Container Registry: DockerHub

Deployment Environment: Linux / EC2 instance

📁 Project Structure
static-website/
│
├── index.html       # Main HTML page
├── style.css        # CSS styles
├── script.js        # JavaScript for interactivity
├── Dockerfile       # Dockerfile for building image
├── docker-compose.yml # Docker Compose file for deployment
└── Jenkinsfile      # Jenkins Declarative Pipeline

🚀 Features

Simple static website with HTML, CSS, and JS

Fully automated CI/CD pipeline with Jenkins

Automatic Docker image build and push to DockerHub

Automatic deployment using Docker Compose

Supports versioned images and rolling updates

🛠️ Prerequisites

Jenkins installed on a Linux server

Docker & Docker Compose installed

DockerHub account (username: shiv201)

GitHub repository: https://github.com/gawalishankar/static-website.git

⚡ Installation & Deployment
1. Clone the Repository
git clone https://github.com/gawalishankar/static-website.git
cd static-website

2. Build Docker Image
docker build -t shiv201/static-web .

3. Run Locally
docker run -d -p 8080:80 shiv201/static-web


Open your browser: http://localhost:8080

4. Deploy using Docker Compose
docker-compose up -d


Access the website at: http://<EC2-PUBLIC-IP>:8080

🔗 CI/CD with Jenkins

Create Jenkins Pipeline using Jenkinsfile from the repo

Add GitHub Webhook to automatically trigger pipeline on code push

Pipeline Stages:

Checkout code from GitHub

Build Docker image

Push image to DockerHub

Deploy container using Docker Compose

✅ Key Outcomes

Fully automated CI/CD pipeline for static website

Fast deployment with Docker and Docker Compose

Continuous integration triggered by GitHub push events
