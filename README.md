# sd-workshop7
### contributors
Sebastian Navia

Steban Amilcar 

# Kubernetes Microservices Project

This project aims to deploy a set of microservices in a Kubernetes cluster. The microservices included in this project are as follows:


- frontend: Main user interface.

- auth-api: User authentication service.

- log-message-processor: Log message processor.

- todos-api: API for managing to-do tasks.

- users-api: API for managing users.

you'll find YAML files needed to deploy each microservice in the Kubernetes cluster:

## Configuration and Deployment

To deploy the microservices in your Kubernetes cluster, follow these steps:

1. Make sure you have `kubectl` installed to interact with the Kubernetes cluster.

2. Use the following commands to deploy each microservice:

```bash
kubectl apply -f kubernetes/frontend.yaml
kubectl apply -f kubernetes/auth-api.yaml
kubectl apply -f kubernetes/log-message-processor.yaml
kubectl apply -f kubernetes/todos-api.yaml
kubectl apply -f kubernetes/users-api.yaml
kubectl apply -f kubernetes/redis.yaml
