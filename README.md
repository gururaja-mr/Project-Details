🚀 Project Details – POCs


This repository contains details of Proof of Concepts (POCs) developed as part of various software architecture, deployment, and cloud-native application exercises. The two primary projects are:

📦 Logistics-Management-App

🛒 ATLAN-Ecommerce-App

1️⃣ Logistics-Management-App

A React + .NET-based logistics shipment management system that enables efficient shipment tracking and management.

Features
Role-based authentication (Admin, Manager, Viewer)

Token-based API security

Shipment CRUD operations with confirmation dialogs

Integrated with a custom backend API

Responsive and interactive UI

Tech Stack
Frontend: React.js

Backend: .NET Web API

Database: SQL Server

Auth: Custom token-based authentication

2️⃣ ATLAN-Ecommerce-App

A full-stack microservices-based ecommerce application deployed on Kubernetes/OpenShift.

🔗 Live Demo: Frontend Application
📦 Source Code: GitHub Repo

Architecture Overview
Frontend: React.js (Port 3000)

Backend: Node.js REST API (Port 5000)

Message Broker: Node.js service with RabbitMQ integration

Database: MongoDB

Message Queue: RabbitMQ

Deployment Steps
1. Clone Repository
bash
Copy
Edit
git clone https://github.com/mrudraia1/ecommerce-app.git
cd ecommerce-app
2. Create Namespace
bash
Copy
Edit
kubectl apply -f ecommerce-k8s/namespace.yaml
3. Build & Push Images
Update image registry in Makefile or deployment manifests.

bash
Copy
Edit
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
4. Deploy Databases
bash
Copy
Edit
kubectl apply -f ecommerce-k8s/mongodb
kubectl apply -f ecommerce-k8s/rabbitmq
Kubernetes & OpenShift Features
ConfigMaps & Secrets for configurations and sensitive data

Ingress Controller for frontend exposure

Persistent Volumes for MongoDB & RabbitMQ

Security Policies via PodSecurityPolicies & Admission Controllers

Monitoring with kubectl top pods and Prometheus/Grafana (optional)

Horizontal Pod Autoscaling based on CPU/Memory usage

Troubleshooting Scenarios
Frontend not accessible: Check Ingress & networking configs

Backend-DB disconnections: Validate ConfigMaps & Secrets

Order processing delays: Analyze RabbitMQ queue performance

Monitoring & Scaling
Resource Usage:

bash
Copy
Edit
kubectl top pods -n ecommerce
Autoscaling: Configurable averageUtilization for frontend & backend services

📜 License
This project is released as part of a POC portfolio and is not licensed for commercial use without permission.
