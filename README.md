# Coffee House - CI/CD & GitOps Project

A simple Flask-based Coffee House web application demonstrating an automated CI/CD and GitOps workflow.

## Architecture

Developer
↓
GitHub
↓
GitHub Actions
↓
Docker Image Build
↓
GitHub Container Registry (GHCR)
↓
Kubernetes Manifest Update
↓
Argo CD
↓
Kubernetes / K3s
↓
Coffee House Application

## Technologies

- Python
- Flask
- HTML/CSS
- Git
- GitHub
- GitHub Actions
- Docker
- GitHub Container Registry (GHCR)
- Kubernetes / K3s
- Argo CD

## Application

The Coffee House application is a lightweight Flask web application with a simple web interface.

The application includes:

- Coffee House homepage
- Flask backend
- HTML/CSS frontend
- Health check endpoint
- Docker containerization
- Kubernetes deployment

## CI/CD Workflow

GitHub Actions automates the application build and container image publishing process.

When application code is pushed to the `main` branch:

1. GitHub Actions checks out the source code.
2. Docker builds the application image.
3. The image is tagged using the Git commit SHA.
4. The image is pushed to GitHub Container Registry.
5. The Kubernetes deployment manifest is automatically updated with the new image version.
6. The updated manifest is committed to GitHub.

This removes the need to manually change image versions such as `v1`, `v2`, or `v3`.

## GitOps Deployment

Argo CD monitors the Kubernetes manifests stored in the GitHub repository.

When the Kubernetes manifest changes, Argo CD automatically synchronizes the desired state from Git to the Kubernetes cluster.

GitHub Repository
       ↓
    Argo CD
       ↓
 Kubernetes
       ↓
 Coffee House

Argo CD Auto-Sync is enabled for the application.
