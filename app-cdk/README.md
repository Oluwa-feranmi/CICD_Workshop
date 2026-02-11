# 🚀 Production Infrastructure — AWS CDK (Python)

This directory contains the **production cloud infrastructure** for the CI/CD Workshop project, implemented using **AWS Cloud Development Kit (CDK) with Python** and Infrastructure as Code (IaC) best practices.

It demonstrates how to **design, provision, and manage scalable AWS infrastructure using modern engineering workflows.**

---

## 🧠 Project Overview

This module is responsible for **automated provisioning and deployment of production infrastructure on AWS**.

It is designed to reflect **real-world engineering practices**, including:

- Infrastructure as Code (IaC)
- Secure cloud provisioning
- Repeatable deployments
- Environment isolation
- Production-grade architecture design

---

## 🏗️ Architecture Summary

**Deployment Flow:**
CI Pipeline → AWS CDK → CloudFormation → AWS Infrastructure


**Key AWS Services Provisioned:**

- AWS CloudFormation (via CDK)
- IAM (roles and security policies)
- Compute and application deployment resources
- Supporting AWS infrastructure services

*(Exact resources depend on stack configuration.)*

---

## 🔧 Key Features

- Infrastructure as Code using AWS CDK (Python)
- Automated production environment provisioning
- Secure IAM role and permission configuration
- Version-controlled cloud deployments
- Scalable architecture patterns
- Production-ready workflow design

---

## 🛠️ Technologies Used

- AWS CDK (Python)
- AWS CloudFormation
- Python
- AWS CLI
- Infrastructure as Code (IaC)

---

## 🎯 Skills Demonstrated

- Cloud infrastructure architecture
- AWS provisioning automation
- Infrastructure as Code (IaC)
- Secure cloud deployments
- CI/CD pipeline integration
- Industry best practices

---

## 🚀 Deployment

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cdk bootstrap
cdk deploy


