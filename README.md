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








for my revision:
✅ 1. Created a simple application (app.py)

What you did

Created a small Python Flask app that returns a message in browser

Why

DevOps engineers don’t focus on app complexity

The app exists so we can:

Containerize it

Deploy it

Manage it

👉 The focus is deployment, not coding.

✅ 2. Defined dependencies (requirements.txt)

What you did

Listed flask as a dependency

Why

Every environment (Docker, server, Kubernetes) must know:

“What packages are required to run this app?”

This makes the app reproducible.

✅ 3. Containerized the app using Docker (Dockerfile)

What you did

Wrote a Dockerfile that:

Uses Python base image

Copies app files

Installs dependencies

Runs the app

Why Docker

Docker packages:

App

Dependencies

Runtime

Eliminates “works on my machine” issues

👉 This is how modern apps are shipped.

✅ 4. Built a Docker image

What you did

docker build -t devops-app .


Why

Docker image = packaged version of your app

Kubernetes and cloud platforms run images, not source code

✅ 5. Verified the app using Docker

What you did

docker run -p 5000:5000 devops-app


Why

Always test locally before Kubernetes

Confirms:

Dockerfile is correct

App runs as expected

✅ 6. Set up Kubernetes using Minikube

What you did

Installed Minikube

Started a local Kubernetes cluster

Why

Companies don’t run apps using docker run

They use Kubernetes for:

Scaling

Self-healing

Load balancing

👉 Minikube simulates a real Kubernetes cluster.

✅ 7. Created Kubernetes Deployment (deployment.yaml)

What you did

Defined:

App name

Docker image

Replicas (2)

Container port

Why

Deployment tells Kubernetes:

“Run this app and keep it running”

Kubernetes:

Creates Pods

Restarts them if they fail

✅ 8. Faced ImagePullBackOff (REAL ISSUE)

What happened

Pods failed to start

Kubernetes couldn’t find the Docker image

Why this happened

Image was local

Kubernetes tried pulling from Docker Hub

👉 This is very common in real projects.

✅ 9. Fixed image issue professionally

What you did

Loaded local image into Minikube:

minikube image load devops-app


Updated Deployment:

imagePullPolicy: IfNotPresent


Why

Tells Kubernetes:

“Use local image if available”

This shows real debugging skill, not copy-paste.

✅ 10. Restarted deployment (Rolling Update)

What you did

kubectl rollout restart deployment devops-app


Why

Applies updated configuration

Demonstrates rolling updates (zero-downtime concept)

✅ 11. Created Kubernetes Service (service.yaml)

What you did

Created a NodePort service

Why

Pods have no stable IP

Service provides:

Stable access

Load balancing

✅ 12. Accessed app via Kubernetes

What you did

minikube service devops-app-service


Why

Confirms:

App is reachable

Kubernetes networking works

🎉 This proves end-to-end deployment.

✅ 13. Used Git & GitHub professionally

What you did

Initialized Git repo

Fixed large file issue

Used .gitignore

Pushed clean code to GitHub using PAT

Why

Version control is mandatory in real projects

Shows professional workflow
