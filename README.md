# Kubernetes Labs

This repository contains hands-on Kubernetes labs and practical exercises performed as part of my DevOps learning journey.

---

# Lab 1: Basic Kubernetes Deployment and Scaling

## Objective

Practice basic Kubernetes operations using Minikube, including cluster creation, Deployment management, and scaling.

## Environment

- OS: Rocky Linux
- Kubernetes: Minikube
- Container Runtime / Driver: Docker
- Tool: kubectl
- Application Image: MySQL 8.0

## Lab Steps

### 1. Start Minikube Cluster

Create a Minikube cluster with two nodes, using Docker as the driver, 2048 MB memory, and 2 CPUs:

```bash
minikube start --nodes=2 --driver=docker --memory=2048 --cpus=2
```

Verify the cluster nodes:

```bash
kubectl get nodes
```

### 2. Create MySQL Deployment

Create a Deployment using the MySQL 8.0 image:

```bash
kubectl create deployment mysql --image=mysql:8.0
```

Configure the MySQL root password:

```bash
kubectl set env deployment/mysql MYSQL_ROOT_PASSWORD=root123
```

### 3. Scale the Deployment

Increase the number of replicas:

```bash
kubectl scale deployment mysql --replicas=3
```

### 4. Verify the Deployment

Check the Deployment status:

```bash
kubectl get deployments
```

Check the Pods:

```bash
kubectl get pods
```

Check the rollout status:

```bash
kubectl rollout status deployment/mysql
```

## What I Learned

- Creating a multi-node Kubernetes cluster using Minikube.
- Understanding Kubernetes Nodes.
- Creating Deployments using kubectl.
- Configuring environment variables in a Deployment.
- Scaling Deployments using replicas.
- Monitoring Deployment and Pod status.
