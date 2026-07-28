# Kubernetes Deployment with Persistent Volumes, ConfigMaps, Secrets, and Services

## 📌 Project Overview

This project demonstrates the deployment of a **two-tier WordPress and MySQL application** on Kubernetes using core Kubernetes resources. The implementation focuses on persistent storage, secure credential management, externalized configuration, and service networking to build a scalable and production-ready application.

---

## 🎯 Objectives

* Deploy WordPress and MySQL as separate Kubernetes workloads.
* Persist MySQL database data using Persistent Volumes.
* Store sensitive database credentials securely using Kubernetes Secrets.
* Externalize application configuration with ConfigMaps.
* Enable communication between application components using Kubernetes Services.
* Follow Kubernetes best practices with declarative YAML manifests.

---

## 🏗️ Architecture

The application consists of the following Kubernetes resources:

* **PersistentVolume (PV)** – Provides persistent storage for MySQL database files.
* **PersistentVolumeClaim (PVC)** – Requests storage from the PersistentVolume.
* **Secret** – Stores MySQL username, password, and root password securely.
* **ConfigMap** – Stores non-sensitive WordPress configuration values.
* **MySQL Deployment** – Runs the MySQL database container.
* **WordPress Deployment** – Runs the WordPress application container.
* **ClusterIP Service** – Provides internal communication between WordPress and MySQL.
* **NodePort Service** – Exposes the WordPress application for external access.

---

## 🛠️ Technologies Used

* Kubernetes
* kubectl
* Docker
* WordPress
* MySQL 8
* YAML
* Minikube / Amazon EKS

---

## 📂 Project Structure

```text
kubernetes-deployment-using-pv/
│
├── Required YAML files/
│
├── Screenshots/
│
├── Architecture.png
├── README.md
├── mysql-deployment.yaml
├── mysql-pv.yaml
├── mysql-pvc.yaml
├── mysql-secret.yaml
├── mysql-service.yaml
├── wordpress-configmap.yaml
├── wordpress-deployment.yaml
└── wordpress-service.yaml
```

---

## 🚀 Deployment Steps

### 1. Create Secret

```bash
kubectl apply -f mysql-secret.yaml
```

### 2. Create ConfigMap

```bash
kubectl apply -f wordpress-configmap.yaml
```

### 3. Create Persistent Volume

```bash
kubectl apply -f persistent-volume.yaml
```

### 4. Create Persistent Volume Claim

```bash
kubectl apply -f persistent-volume-claim.yaml
```

### 5. Deploy MySQL

```bash
kubectl apply -f mysql-deployment.yaml
kubectl apply -f mysql-service.yaml
```

### 6. Deploy WordPress

```bash
kubectl apply -f wordpress-deployment.yaml
kubectl apply -f wordpress-service.yaml
```

---

## 🔍 Verify Deployment

Check Pods

```bash
kubectl get pods
```

Check Services

```bash
kubectl get svc
```

Check Persistent Volumes

```bash
kubectl get pv
```

Check Persistent Volume Claims

```bash
kubectl get pvc
```

Describe Resources

```bash
kubectl describe pod <pod-name>
kubectl describe pvc
kubectl describe service wordpress
```

---

## 🌐 Access the Application

If using NodePort:

```bash
minikube service wordpress
```

or

```text
http://<Node-IP>:<NodePort>
```

If deployed on Amazon EKS:

```text
http://<LoadBalancer-DNS>
```

---

## 📊 Key Features

* Persistent MySQL storage using PV and PVC
* Secure password management with Kubernetes Secrets
* Externalized configuration using ConfigMaps
* Internal networking through ClusterIP Service
* External application access using NodePort or LoadBalancer
* Declarative Infrastructure as Code using YAML manifests
* Easy deployment and maintenance with kubectl

---

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

* Kubernetes storage management
* Persistent Volumes and Persistent Volume Claims
* ConfigMaps and Secrets
* Multi-tier application deployment
* Kubernetes Services and networking
* Deployments and ReplicaSets
* Declarative Kubernetes resource management
* Troubleshooting Kubernetes workloads using kubectl

---

## ✅ Project Outcome

Successfully deployed a production-style two-tier WordPress and MySQL application on Kubernetes with persistent storage, secure credential management, externalized configuration, and reliable service networking. The project demonstrates core Kubernetes concepts required for deploying and managing stateful containerized applications in real-world environments.

## 👨‍💻 Author

**Manoj Kumar Nagamulla**

- GitHub: https://github.com/ManojKumar8244
