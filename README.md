# 🚀 Jenkins CI Pipeline – Docker Image Build & Push

This project implements a **complete Continuous Integration (CI) pipeline** using **Jenkins**, **Docker**, and **GitHub**, where application code is automatically built into a Docker image and pushed to **Docker Hub**.

---

## 📌 Project Overview

This pipeline automates the following workflow:
      
      GitHub → Jenkins → Docker Build → Docker Hub

On every successful Jenkins run:
1. Source code is fetched from GitHub
2. A Docker image is built using a Dockerfile
3. The image is tagged using the Jenkins build number
4. Jenkins logs in securely to Docker Hub
5. The image is pushed to Docker Hub

---

## 🛠️ Technologies Used

- Jenkins – CI automation
- Docker – Containerization
- Docker Hub – Image registry
- Git & GitHub – Version control
- Nginx – Web server
- Linux (Ubuntu) – Jenkins host OS

---

## 📂 Project Structure
my-docker-app/
├── Dockerfile
├── Jenkinsfile
├── index.html
└── README.md

---

## 🐳 Dockerfile

```dockerfile
FROM nginx:1.25-alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80

---

## ⚙️ Jenkins Pipeline Stages

The pipeline consists of the following stages:

### 🧾 1. Checkout SCM
Jenkins automatically pulls the project code from the linked GitHub repository.

### 🏗️ 2. Build Docker Image
Jenkins builds the Docker image based on your `Dockerfile` and tags it using the Jenkins build number.

### 🔐 3. Docker Hub Login
Jenkins logs in to Docker Hub using securely stored credentials.

### 📤 4. Push Docker Image
Jenkins pushes the tagged image to your Docker Hub repository.

---

## 🔐 Credentials Management

- Docker Hub credentials are stored securely in **Jenkins Credentials**
- The credential ID used in the pipeline is:

dockerhub-creds

- Sensitive data like passwords are **NOT hardcoded** inside the Jenkinsfile.

---

## 🏷️ Docker Image Versioning

Images are versioned using Jenkins build numbers.

Examples:

meghaamanickam/meghaa-app:1
meghaamanickam/meghaa-app:2
meghaamanickam/meghaa-app:3
meghaamanickam/meghaa-app:4


Benefits:
- 📌 Clear version tracking  
- 🔄 Easy rollback to a previous build  
- 📊 Better traceability between Git commits and Docker images

---

## ▶️ How to Run

1. Install Jenkins and Docker on a Linux machine.
2. Install the following Jenkins plugins:
   - Git
   - GitHub
   - Docker Pipeline
   - Credentials Binding
3. Add your Docker Hub credentials in Jenkins (ID: `dockerhub-creds`).
4. Create a **Pipeline** job in Jenkins.
5. Link the job to this GitHub repository.
6. Run **Build Now** or trigger via webhook on GitHub push.

---

## ✅ Result

When the pipeline runs successfully:

- Docker image is built
- Image is pushed to Docker Hub
- Jenkins build output shows:

Finished: SUCCESS

---

## 🎯 Key Learnings

With this pipeline you learned:

- CI setup with Jenkins
- Automatic Docker builds
- Secure credential management
- Docker image versioning
- Automation of pushes to Docker Hub

---

## 🚀 Future Enhancements

Here are some improvements you can add:

- ⏱  GitHub webhook automation
- ☸️  Kubernetes deployment (MicroK8s)
- 🔔  CI notifications (Slack / Email)
- 📦 Full CI/CD workflow with deployment stages

---

## 👩‍💻 Author

**Meghaa Manickam**  
DevOps & Cloud Enthusiast

---
