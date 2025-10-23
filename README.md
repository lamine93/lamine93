# ☁️ Cloud & DevOps Portfolio – Mouhamadou LY

Welcome to my **Cloud & DevOps Projects Portfolio** 👋  
This repository showcases my hands-on projects across **AWS** and **Microsoft Azure**,  
with a focus on **Infrastructure as Code (Terraform)**, **container orchestration**, and **automation**.

---

## 🧠 About Me

I’m an HPC and Cloud Engineer passionate about automation, scalability, and infrastructure design.  
I build production-grade architectures on **AWS** and **Azure** using **Terraform**, **Docker**, and **CI/CD pipelines**.

- 🌍 Multi-Cloud: AWS & Azure  
- ⚙️ IaC: Terraform, Bicep  
- 🐳 Containers: Docker, ECS, AKS  
- 🔒 Security: IAM, Secrets Manager, Key Vault  
- 📊 Monitoring: CloudWatch, Azure Monitor  

---

## 🚀 Projects Overview

### 🟧 AWS Projects

| # | Project | Description | Key Technologies |
|---|----------|--------------|------------------|
| 1️⃣ | [Serverless API](./aws/01-serverless-api) | REST API using Lambda, API Gateway & DynamoDB | AWS Lambda, API Gateway, DynamoDB, Cognito, Terraform |
| 2️⃣ | [IaC Deployment](./aws/02-iac-terraform) | Automated serverless stack deployment | Terraform, IAM, Lambda |
| 3️⃣ | [Three-Tier Web App](./aws/03-ecs-three-tier) | Flask API on ECS Fargate + RDS + ALB | ECS, RDS, ALB, Secrets Manager |
| 4️⃣ | [Monitoring & Scaling](./aws/04-monitoring) | ECS Auto Scaling with CloudWatch | CloudWatch, ECS, Terraform |
| 5️⃣ | [CI/CD Pipeline](./aws/05-ci-cd) | GitHub Actions deploying Docker images to ECS | GitHub Actions, ECR, Terraform |

---

### 🟦 Azure Projects

| # | Project | Description | Key Technologies |
|---|----------|--------------|------------------|
| 1️⃣ | [VM Scale Set Deployment](./azure/01-azure-vm-scale-set) | Scalable web app with Azure VM Scale Sets | VMSS, Azure Load Balancer, Terraform |
| 2️⃣ | [Container Apps](./azure/02-azure-container-apps) | Deploying Flask API using Azure Container Apps | ACA, ACR, Bicep |
| 3️⃣ | [AKS with Terraform](./azure/03-terraform-aks-deployment) | Kubernetes cluster managed via Terraform | AKS, Terraform, Helm |
| 4️⃣ | [Azure Functions API](./azure/04-serverless-api) | Serverless API with Cosmos DB backend | Azure Functions, Cosmos DB |

---

## 🧰 Tech Stack Summary

| Category | AWS | Azure |
|-----------|-----|--------|
| **Compute** | ECS Fargate, Lambda | VMSS, Container Apps, AKS |
| **Database** | RDS, DynamoDB | Azure SQL, Cosmos DB |
| **IaC** | Terraform | Terraform, Bicep |
| **Secrets** | Secrets Manager | Key Vault |
| **Networking** | VPC, ALB | VNet, Load Balancer |
| **Monitoring** | CloudWatch | Azure Monitor |

---

## 📊 Architecture Example

```mermaid
graph TD
A[User] --> B[Load Balancer]
B --> C[ECS / AKS Cluster]
C --> D[(Database)]
C --> E[Secrets Manager / Key Vault]
