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
### 2. Deploy the mysql Database and the WordPress:

```sh
kubectl apply -f .
```

### 3. Configuration
Ensure the following environment variables are set correctly in your Kubernetes manifests:

__MYSQL_ROOT_PASSWORD__: Root password for MySQL

__MYSQL_DATABASE__: Database name

__MYSQL_USER__: Database user

__MYSQL_PASSWORD__: Database user password

__WORDPRESS_DB_HOST__: MySQL service name

__WORDPRESS_DB_USER__: Database user for WordPress

__WORDPRESS_DB_PASSWORD__: Password for the WordPress database user

__WORDPRESS_DB_NAME__: WordPress database name

### 4. Verify Deployment
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

