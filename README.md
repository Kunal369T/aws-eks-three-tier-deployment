# AWS EKS Three-Tier Application Deployment

## Overview

This project showcases the deployment of a production-style **three-tier application** on **Amazon EKS** using **Docker**, **Kubernetes**, **Amazon ECR**, **Helm**, and the **AWS Load Balancer Controller**.

The application consists of a **React frontend**, **Node.js backend**, and **MongoDB database**, exposed to the internet through an **Application Load Balancer (ALB)**.

---

## Architecture

```
                Internet
                    │
                    ▼
      AWS Application Load Balancer
                    │
              Kubernetes Ingress
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
  Frontend Service      Backend Service
                                │
                                ▼
                         MongoDB Service
```

---

## Tech Stack

**Cloud:** AWS EC2, Amazon EKS, Amazon ECR, IAM, ALB

**DevOps:** Docker, Kubernetes, Helm, AWS Load Balancer Controller, Git, Linux

**Application:** React, Node.js, MongoDB

---

## Deployment Workflow

- Built Docker images for the frontend and backend.
- Pushed images to Amazon ECR.
- Provisioned an Amazon EKS cluster using `eksctl`.
- Deployed the application using Kubernetes manifests.
- Installed the AWS Load Balancer Controller with Helm.
- Configured Kubernetes Ingress to provision an internet-facing ALB.
- Successfully exposed the application via the ALB DNS endpoint.

---

## Kubernetes Resources

- Namespace
- Deployments
- Services
- Secrets
- Ingress

---

## Challenges & Fixes

### Backend Pod - `CreateContainerConfigError`

- **Cause:** Missing Kubernetes Secret (`mongo-sec`)
- **Fix:** Created the required Secret before deploying the backend.

### ALB Address Not Generated

- **Cause:** Outdated IAM policy for the AWS Load Balancer Controller.
- **Fix:** Updated the IAM policy and restarted the controller.

---

## Skills Demonstrated

- Docker & Amazon ECR
- Amazon EKS
- Kubernetes Deployments, Services, Secrets & Ingress
- Helm
- IAM Roles & Policies
- AWS Load Balancer Controller
- Kubernetes Troubleshooting

---

## Future Improvements

- Provision infrastructure using Terraform
- Automate deployment with GitHub Actions
- Enable HTTPS using AWS Certificate Manager
- Add monitoring with Prometheus & Grafana

---

## What I Learned

- Deploying containerized applications on Amazon EKS.
- Managing Kubernetes resources in a production-like environment.
- Integrating AWS services such as ECR, ALB, and IAM with Kubernetes.
- Troubleshooting Kubernetes configuration and IAM permission issues.
