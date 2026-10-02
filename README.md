# cicd-pipeline-train-schedule-pipelines App Deployes to Kubernetes 


This is a simple train schedule app written using nodejs. It is intended to be used as a sample application for a series of hands-on learning activities.
Your CI/CD pipeline is Follows Above Process:

CI/CD Pipeline Process Flow (GitHub Actions → Docker Hub → Kubernetes)

Developer
    │
    ▼
1. Developer writes application code
    │
    ▼
2. Git Commit
    │
    ▼
3. Git Push to GitHub (main branch)
    │
    ▼
4. GitHub Actions Pipeline Triggered
    │
    ▼
5. Checkout Source Code
       - actions/checkout
    │
    ▼
6. Setup Node.js Environment
       - Install Node.js
       - Configure npm cache
    │
    ▼
7. Install Application Dependencies
       - npm install
    │
    ▼
8. Execute Unit Tests
       - npm test
    │
    ▼
9. Login to Docker Hub
       - Authenticate using GitHub Secrets
    │
    ▼
10. Build Docker Image
       - docker build
       - Tag with Git Commit SHA
       - Tag with latest
    │
    ▼
11. Push Docker Image
       - Push SHA tag
       - Push latest tag
    │
    ▼
12. Copy Kubernetes Manifests
       - SCP k8s manifests to Kubernetes Master Node
    │
    ▼
13. SSH to Kubernetes Control Plane
       - Authenticate using SSH Key
    │
    ▼
14. Update Kubernetes Deployment
       - Replace Docker Image Tag
       - kubectl apply namespace
       - kubectl apply deployment
       - kubectl apply service
    │
    ▼
15. Kubernetes Rolling Update
       - New Pods Created
       - Old Pods Terminated
       - Zero Downtime Deployment
    │
    ▼
16. Verify Deployment
       - kubectl rollout status
       - kubectl get pods
       - kubectl get service
    │
    ▼
17. Application Successfully Deployed
       - Running on Kubernetes Cluster

Pipeline Summery :-

Git Push
|
GitHub Actions
|
Checkout
|
Setup Node
|
npm install
|
Unit Tests
|
Docker Build
|
Docker Push
|
Copy Kubernetes YAML
|
SSH to Kubernetes Master
|
kubectl apply
|
Rolling Update
|
Deployment Verification
|
Application Live
