# Eks-Project

## Overview
Eks-Project is a Kubernetes-based project designed to deploy a WordPress application with a MySQL database. This project uses StatefulSets, PersistentVolumeClaims (PVCs), and Services to ensure data persistence and stable network endpoints.

## Prerequisites
- Kubernetes cluster
- kubectl configured to interact with your cluster
- Docker installed

## Setup

### 1. Clone the Repository
```sh
git clone https://github.com/noalotan/Eks-Project.git
cd Eks-Project
```
### 2. Deploy the MySQL Database
Create the StatefulSet, PVC, and Service for the MySQL database:
```sh
kubectl apply -f mysql-statefulset.yml
kubectl apply -f mysql-pvc.yml
kubectl apply -f mysql-service.yml
```
### 3. Deploy WordPress
Create the Deployment and Service for WordPress:
```sh
kubectl apply -f wordpress-deployment.yml
kubectl apply -f wordpress-service.yml
```
### 4. Configuration
Ensure the following environment variables are set correctly in your Kubernetes manifests:
__MYSQL_ROOT_PASSWORD__: Root password for MySQL

__MYSQL_DATABASE__: Database name

__MYSQL_USER__: Database user

__MYSQL_PASSWORD__: Database user password

__WORDPRESS_DB_HOST__: MySQL service name

__WORDPRESS_DB_USER__: Database user for WordPress

__WORDPRESS_DB_PASSWORD__: Password for the WordPress database user

__WORDPRESS_DB_NAME__: WordPress database name

### 5. Verify Deployment
Check the StatefulSet:
```sh
kubectl get statefulsets
```

Check the PVC:
```sh
kubectl get pvc
```

Check the Service:
```sh
kubectl get svc
```

__Access WordPress:__
Open your browser and navigate to http://<your-cluster-ip>:8080


