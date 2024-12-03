# EKS: Flask App with Stateful Sets

This repository contains the code and Kubernetes manifests for deploying a Flask-based web application on Amazon EKS. The application retrieves a background image from a private S3 bucket and displays it on the homepage. The image URL and other configuration values are stored in a ConfigMap.

## Setup

### Prerequisites
- AWS Account with IAM permissions for EKS, ECR, S3, etc.
- eksctl installed
- kubectl installed
- Docker installed

### Steps

1. **Build and Push Docker Image**
   - Build the Docker image for the Flask app and push it to ECR.

2. **Create EKS Cluster**
   - Create the EKS cluster using `eksctl`.

3. **Deploy MySQL and Flask App**
   - Apply the Kubernetes manifests (`kubectl apply -f k8s/`) to deploy MySQL and the Flask app.

4. **Set up CI/CD with GitHub Actions**
   - Configure GitHub Actions to automatically build and push Docker images.

5. **Configure Flux for Automatic Deployment (Optional)**
   - Use Flux to sync Kubernetes manifests from GitHub.

### Accessing the Application

Once deployed, access the Flask app via the external LoadBalancer URL provided by the Kubernetes service.
