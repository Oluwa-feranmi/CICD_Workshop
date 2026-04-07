# CI/CD Workshop — Production-Grade Pipeline (AWS CDK + CodePipeline)

[![Python](https://img.shields.io/badge/Python-3.9-blue)](https://www.python.org/)
[![AWS CDK](https://img.shields.io/badge/AWS-CDK-orange)](https://aws.amazon.com/cdk/)
[![Flask](https://img.shields.io/badge/Flask-2.0-green)](https://flask.palletsprojects.com/)
[![Docker](https://img.shields.io/badge/Docker-blue)](https://www.docker.com/)

This repository demonstrates a **complete, real-world CI/CD pipeline** using **AWS CDK (Infrastructure as Code)**, **AWS CodePipeline**, **CodeBuild**, **ECR**, and **ECS Fargate**. It showcases production-grade DevOps practices: automated testing, containerized deployment, environment separation (test/prod), and secure IaC.

> Built as a hands-on portfolio project to demonstrate job-ready skills in **SRE, Platform Engineering, DevOps, and Cloud Engineering**.

---

## 🏗️ Architecture Overview
Developer → GitHub → AWS CodePipeline
├── CodeBuild (test) → pytest
├── CodeBuild (docker) → Build & push to ECR
└── Deploy to ECS Fargate (Test → Prod)

**Key AWS Resources Provisioned via CDK**:
- **ECR Repository** – Stores Docker images
- **ECS Fargate Services** (Test + Production) – Runs the Flask app
- **CodePipeline + CodeBuild** – Full CI/CD pipeline using your `buildspec_test.yml` and `buildspec_docker.yml`

**Directories**:
- **`my-app/`** – Flask web application (test & containerized deployment)
- **`app-cdk/`** – AWS CDK stacks (ECR + ECS + Pipeline)

---

## 📁 Project Structure
```bash
CICD_Workshop/
├── .gitignore
├── README.md
├── buildspec_docker.yml          # Builds Docker image and pushes to ECR
├── buildspec_test.yml            # Runs pytest and generates reports
├── my-app/                       # Flask web application (Test environment)
│   ├── app.py                    # Main Flask app
│   ├── requirements.txt
│   ├── Dockerfile
│   ├── templates/                # HTML templates (if present)
│   └── tests/                    # pytest tests
├── app-cdk/                      # AWS CDK Infrastructure as Code (Production)
│   ├── app.py                    # CDK app entry point
│   ├── app_cdk/                  # Stack definitions (ECR, ECS, Pipeline)
│   ├── requirements.txt
│   ├── cdk.json
│   └── tests/
└── ...
---
```
## 🚀 How to Run Locally (Recruiter Quick Start)

### 1. Clone the repository
```bash
git clone https://github.com/Oluwa-feranmi/CICD_Workshop.git
cd CICD_Workshop
```
### 2. Run the Flask App Locally (no AWS required)
cd my-app

# Option A: Python virtual environment
```bash
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python app.py
# App will be live at http://localhost:8081
# Health check: http://localhost:8081/healthcheck
```
# Option B: Docker (exactly as deployed in pipeline)
```bash
cd my-app
docker build -t myapp:latest .
docker run -p 8081:8081 myapp:latest
```
### 3. Run Tests Locally
```bash
cd my-app
python -m pytest --junitxml=pytest_reports/junit.xml
```
### 4. Deploy the Full Infrastructure to AWS (Production Pipeline)
Prerequisites:

AWS account with admin permissions
AWS CLI configured (aws configure)
AWS CDK installed (npm install -g aws-cdk)
Python 3.9+
```bash
cd app-cdk

# 1. Create virtual environment
python -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate

# 2. Install dependencies
pip install -r requirements.txt

# 3. Bootstrap CDK (one-time)
cdk bootstrap

# 4. Deploy everything (ECR + ECS Test/Prod + Pipeline)
cdk deploy --all
```
After deployment you will get:

ECR repository URL
Two ECS Fargate services (test + prod)
A fully functional CodePipeline that triggers on code changes

⚠️ Note: This will incur small AWS costs (Fargate, ECR, etc.). Destroy with cdk destroy --all when finished.
🔄 CI/CD Pipeline Stages (What Happens on git push)

Source – Code pulled from GitHub
Test (buildspec_test.yml) – cd my-app → pytest → JUnit report
Build & Push (buildspec_docker.yml) – Builds Docker image → pushes to ECR
Deploy Test – Updates ECS Fargate service in test environment
Deploy Production – Manual approval gate → updates production ECS service


🛠️ Technologies Used

Backend: Flask (Python)
IaC: AWS CDK (Python)
Container: Docker
CI/CD: AWS CodePipeline + CodeBuild
Runtime: ECS Fargate
Registry: Amazon ECR
Testing: pytest


✅ Skills Demonstrated

End-to-end CI/CD pipeline engineering
Infrastructure as Code with AWS CDK
Containerized deployments (Docker → ECR → ECS Fargate)
Environment separation (Test vs Production)
Secure, automated, and observable release process
Production-grade DevOps best practices


👤 Author
Oluwa-feranmi
Platform & Cloud Engineering Enthusiast | SRE | DevOps Engineer

GitHub: @Oluwa-feranmi


Ready to see it in action?
Clone → run locally → or deploy the full AWS pipeline with one cdk deploy command.
This project is intentionally built to be easy for developers to evaluate — just follow the steps above!
Happy coding! 🚀
