# 🚀 Job Portal CI/CD Pipeline using GitHub Actions

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline for a MERN-based Job Portal application using **GitHub Actions**, **Docker**, **Docker Hub**, and **AWS EC2**.

Whenever code is pushed to the GitHub repository, GitHub Actions automatically:

- Builds Docker images
- Logs in to Docker Hub
- Pushes the latest Docker images
- Connects to the AWS EC2 instance via SSH
- Pulls the latest Docker images
- Stops old containers
- Starts new containers using Docker Compose

This enables automated deployments without manual intervention.

---

# 🛠️ Tech Stack

## Cloud
- AWS EC2

## Containerization
- Docker
- Docker Compose

## CI/CD
- GitHub Actions

## Container Registry
- Docker Hub

## Version Control
- Git
- GitHub

## Operating System
- Ubuntu Linux

---

# 📁 Project Structure

```
job-portal/
│
├── frontend/
│   ├── Dockerfile
│   └── ...
│
├── backend/
│   ├── Dockerfile
│   └── ...
│
├── .github/
│   └── workflows/
│       └── deploy.yml
│
├── docker-compose.yml
│
├── .env
│
└── README.md
```

---

# ⚙️ CI/CD Workflow

```
Developer
     │
     ▼
Git Push
     │
     ▼
GitHub Repository
     │
     ▼
GitHub Actions
     │
     ├── Checkout Repository
     ├── Login to Docker Hub
     ├── Build Frontend Image
     ├── Build Backend Image
     ├── Push Images to Docker Hub
     ├── Connect to AWS EC2 using SSH
     ├── Pull Latest Images
     ├── Stop Existing Containers
     └── Start New Containers using Docker Compose
     │
     ▼
Application Updated Successfully
```

---

# 🔓 Required AWS Security Group Ports

Before deployment, allow the following inbound ports in the EC2 Security Group.

| Port | Purpose |
|------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 3000 | Frontend (if exposed) |
| 8000 | Backend API |
| 27017 | MongoDB (only if hosted on EC2 and required) |

> **Note:** Open only the ports your application actually uses. Avoid exposing unnecessary services to the internet.

---

# 📦 Prerequisites

Before running the CI/CD pipeline, ensure the following:

- AWS EC2 instance is running
- Ubuntu installed on EC2
- Docker installed
- Docker Compose installed
- Git installed
- SSH configured
- Docker Hub account created
- GitHub repository created
- GitHub Actions enabled

---

# 🔐 GitHub Secrets Required

Configure the following secrets in your GitHub repository:

| Secret | Description |
|---------|-------------|
| DOCKER_USERNAME | Docker Hub Username |
| DOCKER_PASSWORD | Docker Hub Access Token/Password |
| EC2_HOST | Public IP or DNS of EC2 |
| EC2_USERNAME | Ubuntu User |
| EC2_SSH_KEY | Private SSH Key |

---

# 🚀 Deployment Steps

## 1. Clone Repository

```bash
git clone <repository-url>
cd job-portal
```

---

## 2. Build Docker Images Locally

```bash
docker compose build
```

---

## 3. Run Containers

```bash
docker compose up -d
```

---

## 4. Push Code to GitHub

```bash
git add .

git commit -m "Updated application"

git push origin main
```

---

## 5. GitHub Actions Automatically Performs

- Checks out the repository
- Logs in to Docker Hub
- Builds Docker images
- Pushes images to Docker Hub
- Connects to EC2 using SSH
- Pulls latest images
- Stops existing containers
- Starts updated containers using Docker Compose

No manual deployment is required after pushing code.

---

# 📋 Useful Docker Commands

## Running Containers

```bash
docker ps
```

---

## All Containers

```bash
docker ps -a
```

---

## Docker Images

```bash
docker images
```

---

## View Logs

```bash
docker logs <container-name>
```

---

## Restart Container

```bash
docker restart <container-name>
```

---

## Stop Containers

```bash
docker compose down
```

---

## Start Containers

```bash
docker compose up -d
```

---

# 📂 GitHub Actions Workflow

```
Push Code
     │
     ▼
Checkout Repository
     │
     ▼
Login to Docker Hub
     │
     ▼
Build Docker Images
     │
     ▼
Push Images
     │
     ▼
SSH into EC2
     │
     ▼
docker compose pull
     │
     ▼
docker compose down
     │
     ▼
docker compose up -d
```

---

# 📌 Features

- Automated CI/CD using GitHub Actions
- Dockerized Frontend and Backend
- Docker Hub Integration
- Automated EC2 Deployment
- SSH-based Remote Deployment
- Zero Manual Docker Image Updates
- Version Controlled Deployment Pipeline

---

# 🔮 Future Improvements

- Deploy to Kubernetes
- Argo CD GitOps
- Terraform Infrastructure
- Prometheus Monitoring
- Grafana Dashboards
- Loki & Promtail Logging
- SonarQube Code Analysis
- Trivy Container Image Scanning
- AWS ECR Integration
- Amazon EKS Deployment

---

# 👨‍💻 Author

**Ryyan Khan**

Aspiring DevOps Engineer

**LinkedIn:** https://www.linkedin.com/in/ryyan-khan-521579292/

**GitHub:** https://github.com/<your-github-username>

---

# ⭐ If you like this project, please give it a Star on GitHub!
