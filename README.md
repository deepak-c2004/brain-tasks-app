Brain Tasks App Deployment on AWS EKS 🚀
Project Overview

This project demonstrates how to deploy a React application in a production-ready environment using modern DevOps tools and AWS services.

The application is containerized using Docker, stored in DockerHub, and deployed to an AWS EKS Kubernetes cluster using a CI/CD pipeline built with CodeBuild and CodePipeline


Technologies Used:

GitHub

Docker

DockerHub

Kubernetes

AWS EKS

AWS CodeBuild

AWS CodePipeline

AWS CloudWatch

Project Architecture:

GitHub Repository
        │
        ▼
CodePipeline
        │
        ▼
CodeBuild
(Build Docker Image)
        │
        ▼
DockerHub
(Store Image)
        │
        ▼
EKS Cluster
(Kubernetes Deployment)
        │
        ▼
AWS LoadBalancer
        │
        ▼
React Web Application


Repository Structure:

Brain-Tasks-App
│
├── dist/                # React build files
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── Dockerfile
├── buildspec.yml
└── README.md

Docker Setup
Build Docker Image
docker build -t brain-tasks-app .
Run Container
docker run -p 3000:3000 brain-tasks-app

Open in browser:

http://localhost:3000
DockerHub

The Docker image is stored in DockerHub.

Example repository:

deepakc742004/brain-tasks-app

Example image tag:

deepakc742004/brain-tasks-app:v1.0
Kubernetes Deployment

Deploy the application using:

kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

Check deployment status:

kubectl get pods
kubectl get svc

The application is exposed using a LoadBalancer service.

CI/CD Pipeline

The CI/CD pipeline is implemented using AWS CodePipeline and AWS CodeBuild.

Pipeline stages:

Source – GitHub repository

Build – AWS CodeBuild builds the Docker image

Push Image – Image pushed to DockerHub

Deploy – Application deployed to EKS cluster

Monitoring

Logs and pipeline activity can be monitored using:

AWS CloudWatch

CodeBuild logs

CodePipeline execution history

Accessing the Application

The application is accessible using the AWS LoadBalancer DNS.

Example:

http://<loadbalancer-dns>:3000

