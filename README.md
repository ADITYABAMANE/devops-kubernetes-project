# Containerized Application Deployment on Kubernetes

## Project Overview
This project demonstrates an end-to-end DevOps workflow where a web application is containerized using Docker and deployed on Kubernetes using Minikube. The focus of this project is on container lifecycle management, Kubernetes orchestration, and real-world debugging.

## Tech Stack
- Linux (WSL2)
- Docker
- Kubernetes (Minikube)
- kubectl
- Git & GitHub
- Python (Flask)

## Application Description
A lightweight Python Flask web application created to demonstrate containerization and Kubernetes deployment concepts.

## Project Workflow
1. Developed a simple Python Flask application.
2. Defined application dependencies using a requirements file.
3. Containerized the application using Docker and a custom Dockerfile.
4. Built and tested the Docker image locally.
5. Set up a local Kubernetes cluster using Minikube.
6. Created a Kubernetes Deployment with multiple replicas.
7. Debugged ImagePullBackOff issues by loading the local image into Minikube.
8. Configured imagePullPolicy to ensure Kubernetes uses local images.
9. Performed rolling restarts to apply configuration changes.
10. Exposed the application using a Kubernetes NodePort Service.
11. Accessed the application via the Minikube service URL.
12. Version-controlled the entire project using Git and GitHub.

## Kubernetes Resources Used
- Deployment
- Service (NodePort)

## How to Run the Project
```bash
docker build -t devops-app .
minikube image load devops-app
kubectl apply -f k8s/
minikube service devops-app-service
