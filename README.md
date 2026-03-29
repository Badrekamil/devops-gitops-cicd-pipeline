# 🚀 DevOps GitOps CI/CD Pipeline Project (Jenkins + Kubernetes + ArgoCD)

## 📌 Project Overview

This project demonstrates a complete end-to-end DevOps CI/CD pipeline using a GitOps approach.
The pipeline automates the process of updating Kubernetes deployments without any manual intervention.

---

## 🛠️ Tech Stack

* Jenkins (CI/CD Automation)
* Docker (Container Image - DockerHub)
* Kubernetes (Container Orchestration)
* ArgoCD (GitOps Continuous Deployment)
* GitHub (Version Control)

---

## ⚙️ Architecture

This project follows a GitOps-based architecture where Kubernetes manifests are stored in a separate repository and automatically synced using ArgoCD.

---

## 🔄 Workflow

1. Developer triggers Jenkins pipeline
2. Jenkins updates Docker image tag in Kubernetes manifest (deployment.yaml)
3. Jenkins commits and pushes changes to GitHub (GitOps repo)
4. ArgoCD automatically detects changes
5. ArgoCD syncs and deploys updated application to Kubernetes cluster
6. Application becomes accessible via NodePort service

---

## 📦 Kubernetes Configuration

* Deployment:

  * 2 replicas
  * Container port: 3000

* Service:

  * Type: NodePort
  * Port: 80 → 30007

---

## 🌐 Application Output

Hello from DevOps CI/CD Project 🚀

---

## 🔥 Key Features

* Fully automated CI/CD pipeline
* GitOps-based deployment using ArgoCD
* No manual `kubectl apply` required
* Dynamic image tag updates via Jenkins
* Real-time deployment synchronization
* Scalable Kubernetes deployment

---

## 🧠 Learning Outcomes

* Hands-on experience with Jenkins pipelines
* Understanding of GitOps workflow using ArgoCD
* Kubernetes deployment and service exposure
* Integration of CI/CD with GitHub and DockerHub
* Real-world DevOps project implementation

---

## 📁 Repositories

* Main Project Repo: *(this repository)*
* GitOps Repo (Kubernetes manifests):
  https://github.com/Badrekamil/k8s-manifests

---

## ⚠️ Note

In this project, a pre-built Docker image from DockerHub was used.
The focus was on automating deployment using Jenkins and GitOps principles rather than building images.

---

## 👨‍💻 Author

Badre Kamil
Aspiring DevOps & Cloud Engineer 🚀
