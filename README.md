# 🚀 Jenkins CI Pipeline – Docker Image Build & Push

This repository demonstrates a **real-world Continuous Integration (CI) pipeline** using **Jenkins**, **Docker**, and **GitHub**.  
The pipeline automatically builds a Docker image from source code and pushes it to **Docker Hub** with proper versioning.

---

## 📌 Project Overview

This project automates the following CI workflow:

GitHub → Jenkins → Docker Build → Docker Hub


Whenever the pipeline runs successfully, Jenkins:
- Pulls the latest code from GitHub
- Builds a Docker image using a Dockerfile
- Tags the image using the Jenkins build number
- Authenticates securely with Docker Hub
- Pushes the image to Docker Hub

---

## 🛠️ Technologies Used

- **Jenkins** – Continuous Integration automation
- **Docker** – Containerization platform
- **Docker Hub** – Container image registry
- **Git & GitHub** – Source code management
- **Nginx** – Web server (base image)
- **Linux (Ubuntu)** – Jenkins host OS

---

## 📂 Project Structure

my-docker-app/
├── Dockerfile
├── Jenkinsfile
├── index.html
└── README.md


---

## 🐳 Dockerfile

The application uses a lightweight **Nginx Alpine** image to serve a static web page.

```dockerfile
FROM nginx:1.25-alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80

---
⚙️ Jenkins Pipeline Stages
1️⃣ Checkout SCM
Jenkins automatically checks out the source code from the GitHub repository.

2️⃣ Build Docker Image
The Docker image is built using the Dockerfile and tagged with the Jenkins build number.

3️⃣ Docker Hub Login
Jenkins logs in to Docker Hub using credentials stored securely in Jenkins.

4️⃣ Push Docker Image
The versioned Docker image is pushed to Docker Hub.

---
🔐 Credentials Management
-Docker Hub credentials are stored securely in Jenkins Credentials
-Credential ID used in the pipeline:
      dockerhub-creds
-No sensitive information is hardcoded in the Jenkinsfile

---

🏷️ Docker Image Versioning
Docker images are tagged using Jenkins build numbers:

meghaamanickam/meghaa-app:1
meghaamanickam/meghaa-app:2
meghaamanickam/meghaa-app:3
meghaamanickam/meghaa-app:4

Benefits:
✔ Clear version tracking
✔ Easy rollback to previous builds
✔ Strong build and deployment traceability

---

▶️ How to Run the Pipeline
1.Install Jenkins and Docker on a Linux machine
2.Install required Jenkins plugins:
      -Git
      -GitHub
      -Docker Pipeline
      -Credentials Binding
3.Add Docker Hub credentials in Jenkins (dockerhub-creds)
4.Create a Jenkins Pipeline job
5.Link the job to this GitHub repository
6.Click Build Now or trigger via webhook

---

✅ Result
On successful execution:
      -Docker image is built successfully
      -Image is pushed to Docker Hub
      -Jenkins job status shows:
            Finished: SUCCESS
---

🎯 Key Learnings
-Jenkins pipeline configuration from SCM
-Secure credential management
-Docker image build and push automation
-CI pipeline best practices
-Real-world DevOps workflow implementation

---

🚀 Future Enhancements
-GitHub webhook for automatic triggering
-Kubernetes deployment using MicroK8s
-CI notifications (Slack / Email)
-Extension to a full CI/CD pipeline

---

👩‍💻 Author
Meghaa Manickam
DevOps & Cloud Enthusiast
