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
**## ⚙️ Jenkins Pipeline Stages**

### 1. Checkout SCM
Jenkins automatically pulls the source code from the GitHub repository.

### 2. Build Docker Image
Builds the Docker image and tags it using the Jenkins build number.

### 3. Docker Hub Login
Logs in to Docker Hub using credentials stored securely in Jenkins.

### 4. Push Docker Image
Pushes the versioned Docker image to Docker Hub.

---

## 🔐 Credentials Management

- Docker Hub credentials are stored securely in **Jenkins Credentials**
- Credential ID used: dockerhub-creds
- No sensitive data is hardcoded in the Jenkins pipeline

---

## 🏷️ Docker Image Versioning

Docker images are tagged using Jenkins build numbers:

meghaamanickam/meghaa-app:1
meghaamanickam/meghaa-app:2
meghaamanickam/meghaa-app:3
meghaamanickam/meghaa-app:4

This enables:
- Version tracking
- Easy rollback
- Clear build traceability

---

## ▶️ How to Run

1. Install Jenkins and Docker on a Linux machine
2. Install the required Jenkins plugins:
   - Git
   - GitHub
   - Docker Pipeline
   - Credentials Binding
3. Add Docker Hub credentials in Jenkins
4. Create a Jenkins **Pipeline job**
5. Link the job to this GitHub repository
6. Run **Build Now** or trigger the pipeline using a webhook

---

## ✅ Result

- Docker image built successfully
- Image pushed to Docker Hub
- Jenkins job status:
      Finished: SUCCESS
---

## 🎯 Key Learnings

- Jenkins pipeline configuration from SCM
- Secure credential handling in Jenkins
- Docker image build and push automation
- CI pipeline best practices
- Real-world DevOps workflow implementation

---

## 🚀 Future Enhancements

- GitHub webhook automation
- Kubernetes (MicroK8s) deployment
- CI notifications (Slack / Email)
- Extension to a full CI/CD pipeline

---

## 👩‍💻 Author

**Meghaa Manickam**  
DevOps & Cloud Enthusiast


