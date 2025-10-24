# ☁️ Cloud & DevOps Portfolio – Mouhamadou LY

Welcome to my **Cloud & DevOps Projects Portfolio** 👋  
This repository showcases my hands-on projects across **AWS** and **Microsoft Azure**,  
with a focus on **Infrastructure as Code (Terraform)**, **container orchestration**, and **automation**.

---

## 🧠 About Me

I’m an HPC and Cloud Engineer passionate about automation, scalability, and infrastructure design.  
I build production-grade architectures on **AWS** and **Azure** using **Terraform**, **Docker**, and **CI/CD pipelines**.

- 🌍 Multi-Cloud: AWS & Azure & Google 
- ⚙️ IaC: Terraform  
- 🐳 Containers: Docker, ECS, AKS, GKE, EKS  
- 🔒 Security: IAM, Secrets Manager, Key Vault  
- 📊 Monitoring: CloudWatch, Azure Monitor  

---

## 🚀 Projects Overview

### 🟧 AWS Projects

| # | Project | Description | Key Technologies |
|---|----------|--------------|------------------|
| 1️⃣ | [Serverless API](https://github.com/lamine93/aws-lambda-serverless) | REST API using Lambda, API Gateway & DynamoDB | AWS Lambda, API Gateway, DynamoDB, Cognito, Terraform |
| 2️⃣ | [Three-Tier Web App](https://github.com/lamine93/aws-three-thier-app) | Flask API on ECS Fargate + RDS + ALB | ECS, RDS, ALB, Secrets Manager |
| 3️⃣ | [Monitoring & Scaling](./aws/04-monitoring) | ECS Auto Scaling with CloudWatch | CloudWatch, ECS, Terraform |
| 5️⃣ | [CI/CD Pipeline](https://github.com/lamine93/aws-ecs-fargate) | GitHub Actions deploying Docker images to ECS | GitHub Actions, ECR, Terraform |

---

### 🟦 Azure Projects

| # | Project | Description | Key Technologies |
|---|----------|--------------|------------------|
| 1️⃣ | [Hub Spoke](https://github.com/lamine93/vnet-demo) | Scalable web app with Azure VM Scale Sets | Vnet, Security Group, IAM, Terraform |
| 2️⃣ | [Container Apps](https://github.com/lamine93/container-app) | Deploying Flask API using Azure Container Apps | ACA, ACR, Terraform |
| 3️⃣ | [AKS with Terraform](https://github.com/lamine93/aks-demo) | Kubernetes cluster managed via Terraform | AKS, Terraform, ACR |
| 4️⃣ | [Azure Functions API](https://github.com/lamine93/azure-app-function-v2) | Serverless API with Cosmos DB backend | Azure Functions, Cosmos DB |

---

## 🧰 Tech Stack Summary

| Category | AWS | Azure |
|-----------|-----|--------|
| **Compute** | ECS Fargate, Lambda | VMSS, Container Apps, AKS |
| **Database** | RDS, DynamoDB | Cosmos DB |
| **IaC** | Terraform | Terraform |
| **Secrets** | Secrets Manager | Key Vault |
| **Networking** | VPC, ALB | VNet, Load Balancer |
| **Monitoring** | CloudWatch | Azure Monitor |

---

## 📊 Architecture Examples

 **🏗️ Three-Tier Web Application on AWS**

```mermaid
graph TD
    A[User] -->|HTTP| B[ALB - Public Subnets]
    B -->|Forward Traffic| C[ECS Service Fargate- Private Subnets]
    C -->|DB Connection| D[(Amazon RDS - PostgreSQL)]
    C -->|Secrets| E[AWS Secrets Manager]
```

**🚀 AWS ECS Fargate + ALB Deployment (Terraform)**

```mermaid
graph TD
    A[User] -->|HTTP| B(ALB - Application Load Balancer)
    B -->|Forward traffic| C[ECS Fargate Service]
    C -->|Runs Container| D[Docker App]
    D -->|Logs| E[CloudWatch Logs]
    C -->|Pull Image| F[ECR Repository]
    C -->|Network| G[VPC + Public Subnets + SG]
```

**Azure Hub Spoke topology**


```mermaid
%%{init: {
  "theme": "dark",
  "themeVariables": {
    "primaryColor": "#0b1220",
    "primaryTextColor": "#e5e7eb",
    "primaryBorderColor": "#6b7280",
    "lineColor": "#60a5fa",
    "tertiaryColor": "#0b1220",
    "fontFamily": "ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace",
    "edgeLabelBackground": "#0b1220"
  }
}}%%

flowchart TB
  %% --- TOP: Internet -> VPN/ER ---
  Internet[(🌍 Internet)]
  GW["🔐 VPN / ExpressRoute &nbsp"]
  Internet --> GW

  %% --- HUB ---
  subgraph HUB["💠 **HUB VNet - 10.0.0.0/16**&nbsp"]
    direction TB
    FW["🔥 Azure Firewall<br/>10.0.1.0/24<br/>(AzureFirewallSubnet)"]
    Bastion["🧑‍💻 Azure Bastion<br/>10.0.2.0/24<br/>(AzureBastionSubnet)&nbsp"]
  end

  %% --- SPOKES GROUP ---
  subgraph SPOKES["**Spokes**&nbsp"]
    
    direction LR
    Spoke1["🛰️ Spoke1 (App) &nbsp<br/>10.10.0.0/16<br/>• app-subnet<br/>• NSG"]
    Spoke2["🛰️ Spoke2 (Data)&nbsp<br/>10.20.0.0/16<br/>• data-subnet<br/>• NSG"]
  end

  %% --- FLOWS ---
  GW --> HUB
  HUB == "Peering + UDR&nbsp&nbsp" ==> Spoke1
  HUB == "Peering + UDR&nbsp&nbsp" ==> Spoke2

  %% --- OPTIONALS BOX ---
%%   subgraph OPTIONS["Options"]
%%     direction TB
%%     NAT["↗️ NAT Gateway (egress centralisé)"]
%%     PDNS["📛 Private DNS + Private Endpoints<br/>(KV, ACR, Storage, DB)"]
%%     NOTE["🔭 Bastion pour SSH/RDP (no public IP on VMs)"]
%%   end

  %% --- STYLES ---
  classDef hub    fill:#132a4a,stroke:#60a5fa,stroke-width:2px,color:#f3f4f6;
  classDef spokes fill:#0f3a2e,stroke:#10b981,stroke-width:2px,color:#e7f8f2;
  classDef opts   fill:#1f2937,stroke:#9ca3af,stroke-width:1.5px,color:#e5e7eb;
  class HUB hub;
  class SPOKES spokes;
  class OPTIONS opts;
```
