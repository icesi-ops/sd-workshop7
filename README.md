# Task manager app 

Daniel Jaraba - Samuel Guerrero  

## Overview
This project demonstrates how to containerize an application using Docker and deploy it to a Kubernetes cluster for orchestration. This project is a simple Task Manager application that allows users to create personal tasks and manage them effectively. Users can add, update, delete, and mark tasks as completed.

## Prerequisites
- Docker installed locally ([installation instructions](https://docs.docker.com/get-docker/))
- Kubernetes cluster setup (you can use tools like Minikube or kind for local development, or a cloud-based Kubernetes service)
- kubectl installed locally ([installation instructions](https://kubernetes.io/docs/tasks/tools/install-kubectl/))

## Getting Started
Follow these instructions to get the project up and running on your local machine or Kubernetes cluster.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/danieljaraba/microservice-app-example.git
   cd microservice-app-example
   ```
2. **Kluster Run:**
    ```bash
    kubectl apply -k k8s/.
    

