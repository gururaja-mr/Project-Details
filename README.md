# ☁️ SKF – Global Cloud Operations & Infrastructure Automation

This repository showcases infrastructure automation and cloud operations work done for SKF. The project involved managing multi-account AWS environments, implementing governance, and deploying scalable infrastructure using modern DevOps tools.

## Key Technologies
- Amazon Web Services (AWS)
- Terraform, CloudFormation
- Datadog, Ansible
- ArgoCD, Azure DevOps
- Rancher, Amazon EKS

## Features
- Infrastructure as Code (IaC)
- GitOps-based deployments
- Real-time monitoring and alerting
- Scalable Kubernetes clusters

## Author
[Gururaja Rudraiah]


# 🚗 Mercedes-Benz – HR-Brain & IDEA-Infrastructure Projects

This repository contains infrastructure setup and deployment automation for HR-Brain and IDEA-Infrastructure applications at Mercedes-Benz. The projects were deployed in a hybrid cloud environment using Kubernetes and supported by DevOps best practices.

## Key Technologies
- Harbor (Container Registry)
- Kubernetes (Orchestration)
- Grafana (Monitoring)
- Ansible (Configuration Management)

## Features
- Automated infrastructure provisioning
- Scalable Kubernetes deployments
- Real-time monitoring and alerting
- Hybrid cloud integration

## Author
[Gururaja Rudraiah]




# 🚗 New Car Locator – Volvo Cars

This project was developed as part of my role at Tech Mahindra Ltd for Volvo Cars. It enables users to locate new vehicles across dealerships with real-time data and a user-friendly interface.

## Features
- Real-time car availability
- Advanced filtering options
- Responsive design
- API integration with Volvo systems

## Technologies
React.js | Redux.js | .NET | MSSQL Server | Azure DevOps

## Author
[Gururaja Rudraiah]


# 🏭 Otto Environmental Systems – Enterprise Web Portal

This project was developed as part of my role at BlueChip Computers Pvt Ltd for Otto Environmental Systems. It provides a centralized platform for managing customer orders, product catalogs, and internal workflows.

## Features
- Role-based access control
- Order tracking and reporting
- Product catalog management
- Integration with logistics APIs

## Technologies
ASP.NET | MVC | SQL Server | IIS

## Author
[Gururaja Rudraiah]





# 🚀 Project Details – POCs

This repository contains details of Proof of Concepts (POCs) developed as part of various software architecture, deployment, and cloud-native application exercises. The two primary projects are:

- **📦 Logistics-Management-App**
- **🛒 ATLAN-Ecommerce-App**

---

## 1️⃣ Logistics-Management-App

A **React + .NET**-based logistics shipment management system that enables efficient shipment tracking and management.

### **Features**
- Role-based authentication (**Admin**, **Manager**, **Viewer**)
- Token-based API security
- Shipment CRUD operations with confirmation dialogs
- Integrated with a custom backend API
- Responsive and interactive UI

### **Tech Stack**
- **Frontend:** React.js  
- **Backend:** .NET Web API  
- **Database:** SQL Server  
- **Auth:** Custom token-based authentication  

---

## 2️⃣ ATLAN-Ecommerce-App

A **full-stack microservices-based ecommerce application** deployed on **Kubernetes/OpenShift**.  

🔗 **Live Demo:** [Frontend Application](http://frontend-ecommerce.apps.marula-cl.ocs-osd.syseng.devcluster.openshift.com/)  
📦 **Source Code:** [GitHub Repo](https://github.com/gururaja-mr/ecommerce-app.git)  

### **Architecture Overview**
- **Frontend:** React.js (Port 3000)  
- **Backend:** Node.js REST API (Port 5000)  
- **Message Broker:** Node.js service with RabbitMQ integration  
- **Database:** MongoDB  
- **Message Queue:** RabbitMQ  

---

### **Deployment Steps**


#### **2. Create Namespace**
```bash
kubectl apply -f ecommerce-k8s/namespace.yaml
```

#### **3. Build & Push Images**
Update image registry in `Makefile` or deployment manifests.
```bash
# Backend
make build-backend
make push-backend
kubectl apply -f ecommerce-k8s/backend

# Frontend
make build-frontend
make push-frontend
kubectl apply -f ecommerce-k8s/frontend

# Message Broker
make build-message
make push-message
kubectl apply -f ecommerce-k8s/message
```

#### **4. Deploy Databases**
```bash
kubectl apply -f ecommerce-k8s/mongodb
kubectl apply -f ecommerce-k8s/rabbitmq
```

---

### **Kubernetes & OpenShift Features**
- **ConfigMaps & Secrets** for configurations and sensitive data
- **Ingress Controller** for frontend exposure
- **Persistent Volumes** for MongoDB & RabbitMQ
- **Security Policies** via PodSecurityPolicies & Admission Controllers
- **Monitoring** with `kubectl top pods` and Prometheus/Grafana (optional)
- **Horizontal Pod Autoscaling** based on CPU/Memory usage

---

### **Troubleshooting Scenarios**
- **Frontend not accessible:** Check Ingress & networking configs
- **Backend-DB disconnections:** Validate ConfigMaps & Secrets
- **Order processing delays:** Analyze RabbitMQ queue performance

---

### **Monitoring & Scaling**
- **Resource Usage:**
```bash
kubectl top pods -n ecommerce
```
- **Autoscaling:** Configurable `averageUtilization` for frontend & backend services

---

## 📜 License
This project is released as part of a **POC portfolio** and is not licensed for commercial use without permission.
