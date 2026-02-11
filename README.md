# 🚀 CI/CD Workshop — Production-Grade DevOps Pipeline (AWS & GitHub Actions)

This repository demonstrates a **real-world CI/CD pipeline architecture** using **GitHub Actions**, **AWS**, and **Infrastructure as Code (IaC)** principles. It showcases production-grade DevOps practices including automated testing, cloud provisioning, and deployment automation.

> Built as a hands-on portfolio project to demonstrate job-ready DevOps and Cloud Engineering skills.

---

## 🧠 Project Overview

This project implements a **multi-stage CI/CD deployment pipeline** that automates:

- Continuous Integration (CI)
- Test environment deployment
- Production environment provisioning
- Secure cloud deployments using AWS CDK

The architecture reflects **real enterprise DevOps workflows**, emphasizing:

- Automation
- Security
- Scalability
- Reliability

---

## 🏗️ Architecture Overview
                    ┌───────────────┐
                    │   Developer   │
                    └───────┬───────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │   GitHub Repo     │
                  │  (Source Control) │
                  └─────────┬─────────┘
                            │
                            ▼
              ┌──────────────────────────┐
              │   CI Pipeline            │
              │ (Build, Test, Validate)  │
              └─────────┬────────────────┘
                            │
                            ▼
              ┌──────────────────────────┐
              │ Test Deployment           │
              │       my-app/             │
              └─────────┬────────────────┘
                            │
                            ▼
              ┌──────────────────────────┐
              │ Production Deployment     │
              │        app-cdk/           │
              └─────────┬────────────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │      AWS Cloud     │
                  │ (Provisioned via   │
                  │   AWS CDK - IaC)   │
                  └───────────────────┘

### High-Level Workflow
Developer → GitHub → CI Pipeline → Test (my-app) → Prod (AWS CDK) → AWS Cloud


---

## 🔧 Deployment Environments

### Test Environment — `my-app/`

- Handles application validation and testing
- Ensures correctness before production release
- Simulates CI-based test deployments

### Production Environment — `app-cdk/`

- Uses **AWS CDK (Cloud Development Kit)** for cloud infrastructure provisioning
- Implements **Infrastructure as Code (IaC)**
- Automates deployment of AWS infrastructure and services

---

## 🚦 CI/CD Pipeline Stages

1. Code checkout
2. Automated testing
3. Build & validation
4. Test deployment
5. Production infrastructure provisioning
6. Automated AWS deployment

---

## 🔐 Security & Best Practices

- GitHub encrypted secrets for credential management
- Infrastructure as Code for repeatability
- Environment separation (test & production)
- Fully automated deployments
- No credentials committed to source control

---

## 🛠️ Technologies Used

- GitHub Actions
- AWS CDK
- AWS Cloud Services
- YAML
- Linux Shell Scripting
- Infrastructure as Code (IaC)

---

## 🎯 Skills Demonstrated

- CI/CD pipeline engineering
- Cloud infrastructure automation
- AWS provisioning using CDK
- DevOps best practices
- Secure deployment workflows
- Production-grade architecture design

---

## 👤 Author

**Oluwa-feranmi**  
DevOps & Cloud Engineering Enthusiast 
