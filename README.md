# 🚀 Java Microservices Deployment on Kubernetes

This project demonstrates how to **build, containerize, and deploy a Java microservice** on **Kubernetes** using **Maven**, **Docker**, and **Kubernetes manifests**.

It covers the complete process — from building the application to deploying it on a cluster, exposing it through a NodePort service, and accessing it via endpoints.

---

## 🧰 Tools and Technologies Used

- **Java 17** — Application development  
- **Maven** — Build tool to compile and package the application  
- **Docker** — Containerization of microservices  
- **Kubernetes (Minikube)** — Deployment and orchestration  
- **kubectl** — Command-line tool to manage Kubernetes clusters  
- **Kubernetes Dashboard** — Visualization of workloads and services  

---

## 🏗️ Project Overview

Each microservice is:
1. **Built** using Maven to create a `.jar` file.  
2. **Dockerized** by creating a Docker image.  
3. **Deployed** on Kubernetes using `Deployment` and `Service` YAML manifests.  
4. **Accessed** via NodePort service endpoints exposed on the Kubernetes cluster.

---

## ⚙️ Setup and Deployment Steps

### Clone the Repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```
### Build the Java Application
``` bash
mvn clean package
```
### Build and Push Docker Image
``` bash
docker build -t <your-dockerhub-username>/stockmanager:latest .
docker push <your-dockerhub-username>/stockmanager:latest
docker build -t <your-dockerhub-username>/shopfront:latest .
docker push <your-dockerhub-username>/shopfront:latest
docker build -t <your-dockerhub-username>/productcatalogue:latest .
docker push <your-dockerhub-username>/productcatalogue:latest
```
### Start Minikube
``` bash
minikube start --driver=docker
kubectl get nodes
```
### Deploy the Application on Kubernetes
``` bash
kubectl apply -f k8s/stockmanager-deployment.yml
```

### Verify Deployment
``` bash
kubectl get pods
kubectl get svc
kubectl describe pod <pod-name>
```
### Access the Application
``` bash
minikube service stockmanager --url
or http://<your-ec2-public-ip>:<nodeport>
```
### Screenshots
. Maven build success
. Docker build sucess
. Deployment success
. Kubernetes dashbord
. Application running





