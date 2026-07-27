# Kubernetes Deployment with PV, ConfigMap, Secrets, and Services

## Problem Statement Overview
Modern stateful applications running in Kubernetes require persistent storage, external configuration management, secure credential handling, and network access[cite: 1]. The objective of this project is to deploy a two-tier WordPress and MySQL application using core Kubernetes resources to ensure data persistence, security, and scalability[cite: 1].

## Solution Approach
I designed and deployed a multi-tier WordPress and MySQL application on Kubernetes using standard declarative YAML definitions[cite: 1]:
* **Persistent Storage:** Configured a `PersistentVolume` (PV) and `PersistentVolumeClaim` (PVC) to ensure MySQL data persists across pod restarts[cite: 1].
* **Security & Secrets:** Managed sensitive MySQL database passwords securely using a Kubernetes `Secret`[cite: 1].
* **External Configuration:** Configured application runtime parameters using a `ConfigMap`[cite: 1].
* **Workloads & Networking:** Managed pod lifecycles using `Deployment` objects and exposed WordPress and MySQL using Kubernetes `Service` definitions (NodePort / ClusterIP)[cite: 1].

## Dependencies and Tools
* Kubernetes Cluster (Minikube, EKS, or local cluster)[cite: 1]
* `kubectl` CLI tool[cite: 1]
* Docker Container Images (`wordpress`, `mysql`)[cite: 1]
* YAML Configuration Files[cite: 1]

## Execution Steps
1. **Apply Secret and ConfigMap:**
   ```bash
   kubectl apply -f mysql-secret.yaml
   kubectl apply -f wordpress-configmap.yaml
