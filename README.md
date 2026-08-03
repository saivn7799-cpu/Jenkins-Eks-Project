# Jenkins-EKS-Project

# Jenkins CI/CD Pipeline for AWS EKS Deployment

## Overview

This project demonstrates a **Jenkins CI/CD pipeline** for deploying applications to **Amazon EKS (Elastic Kubernetes Service)**. It automates the deployment workflow by securely authenticating with AWS, configuring Kubernetes access, validating cluster connectivity, and deploying an application to the EKS cluster.

The pipeline includes the following key steps:

Building the Application: (A placeholder stage, adaptable for actual build processes.)
Secure AWS EKS Authentication: Dynamically configures kubectl using Jenkins credential management to interact with a specified EKS cluster.
Connectivity Validation: Verifies the connection to the EKS cluster before proceeding.
Deployment: Deploys a simple Nginx container image to the EKS cluster using kubectl as a demonstration.
This pipeline illustrates how to connect Jenkins to AWS EKS, handle credentials securely, and perform a basic deployment, making it a good starting point for understanding EKS automation with Jenkins.

This project serves as a beginner-friendly example of integrating **Jenkins**, **AWS CLI**, and **Kubernetes (kubectl)** for automated cloud deployments.

---

## Features

- **Declarative Jenkins Pipeline**
- **Secure AWS Credential Management** using Jenkins Credentials
- **Dynamic kubeconfig** generation with AWS CLI
- **EKS Connectivity Validation**
- **Automated Kubernetes Deployment**
- **Configurable AWS Region & Cluster Name**

---

## Tech Stack

- **Jenkins**
- **AWS EKS**
- **Kubernetes (kubectl)**
- **AWS CLI**
- **Groovy (Jenkinsfile)**
- **Docker**

---

## Pipeline Workflow

```
GitHub Repository
        │
        ▼
   Jenkins Pipeline
        │
        ▼
 Build Application
        │
        ▼
 Authenticate to AWS
        │
        ▼
 Configure kubeconfig
        │
        ▼
 Validate EKS Cluster
        │
        ▼
 Deploy Application
```

---

## Pipeline Stages

### **1. Build Application**
- Builds the application (placeholder for Maven, Gradle, or Docker build).

### **2. Configure EKS**
- Authenticates with **AWS** using Jenkins credentials.
- Updates **kubeconfig** for the target EKS cluster.

### **3. Validate Connectivity**
- Verifies communication with the cluster using:

```bash
kubectl get nodes
```

### **4. Deploy Application**
- Deploys a sample **Nginx** application to Amazon EKS.

---

## Prerequisites

- **Jenkins** with Pipeline & Credentials plugins
- **AWS CLI** installed
- **kubectl** installed
- **Amazon EKS Cluster**
- **AWS IAM User/Role** with EKS access
- Jenkins credentials:
  - **jenkins_aws_access_key_id**
  - **jenkins_aws_secret_access_key**

---

## Run the Pipeline

1. Configure AWS credentials in **Jenkins**.
2. Create a **Pipeline Job** using the `Jenkinsfile`.
3. Click **Build Now**.
4. Monitor the execution in **Console Output**.

---

## Customization

You can easily customize the pipeline by:

- Updating the **AWS Region**
- Changing the **EKS Cluster Name**
- Replacing the sample deployment with your own Kubernetes manifests:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---

## Learning Outcome

This project demonstrates how to:

- Build a **Jenkins CI/CD pipeline**
- Securely connect **Jenkins** to **AWS EKS**
- Configure **kubectl** dynamically
- Validate Kubernetes cluster connectivity
- Automate application deployment on **Amazon EKS**
