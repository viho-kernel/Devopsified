# Go Web App - DevOps Learning Platform

A modern web application built with Go that serves as an educational platform for learning DevOps practices. This project demonstrates end-to-end DevOps implementation including CI/CD automation, containerization, infrastructure as code, and Kubernetes orchestration.

## Overview

This Go web application provides a learning hub for DevOps fundamentals, featuring tutorials and courses on various DevOps tools and practices including AWS, Azure, Terraform, Python, Ansible, and GitOps.

## Features

- **Responsive Web Interface** - Multi-page educational platform with Home, About, Contact, and Courses sections
- **CI/CD Pipeline** - Automated GitHub Actions workflow for building, testing, and deploying
- **Docker Support** - Containerized application with multi-stage builds
- **Kubernetes Ready** - Helm charts and Kubernetes manifests for orchestration
- **Infrastructure as Code** - Terraform configurations for AWS EKS deployment
- **Code Quality** - Integrated linting with golangci-lint

## Tech Stack

- **Backend**: Go 1.22
- **Containerization**: Docker
- **Orchestration**: Kubernetes, Helm
- **Infrastructure**: Terraform, AWS EKS
- **CI/CD**: GitHub Actions
- **Static Assets**: HTML5, CSS

## Project Structure

```
go-web-app-main/
├── main.go                 # Application entry point
├── main_test.go           # Unit tests
├── Dockerfile             # Container image definition
├── go.mod                 # Go module dependencies
├── static/                # HTML pages and assets
│   ├── home.html
│   ├── about.html
│   ├── contact.html
│   ├── courses.html
│   └── images/
├── .github/workflows/     # CI/CD automation
│   └── ci.yaml
├── helm/                  # Helm chart for K8s deployment
│   └── go-web-app-chart/
├── k8s/                   # Kubernetes manifests
│   └── manifests/
└── eks/                   # AWS EKS infrastructure
    └── terraform/
```

## Getting Started

### Prerequisites

- Go 1.22+
- Docker
- kubectl
- Helm 3+
- Terraform (for infrastructure deployment)

### Local Development

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd go-web-app-main
   ```

2. **Build and run locally**

   ```bash
   go build -v ./...
   go run main.go
   ```

3. **Run tests**

   ```bash
   go test -v ./...
   ```

4. **Access the application**
   ```
   http://localhost:8080
   ```

### Docker Deployment

1. **Build Docker image**

   ```bash
   docker build -t go-web-app:latest .
   ```

2. **Run container**
   ```bash
   docker run -p 8080:8080 go-web-app:latest
   ```

## CI/CD Pipeline

The GitHub Actions workflow (`ci.yaml`) automatically:

1. **Build & Test** - Compiles Go code and runs test suite
2. **Code Quality** - Runs golangci-lint for linting
3. **Docker Build** - Builds and pushes image to DockerHub
4. **Helm Update** - Updates Helm chart with new image tag

**Trigger**: Pushes to `main` branch (excluding README, Helm, K8s, and GitHub files)

## Kubernetes Deployment

### Using Helm

```bash
helm install go-web-app ./helm/go-web-app-chart -f helm/go-web-app-chart/values.yaml
```

### Using Kubectl

```bash
kubectl apply -f k8s/manifests/
```

## Infrastructure as Code (Terraform)

Deploy to AWS EKS cluster:

```bash
cd eks/terraform/
terraform init
terraform plan
terraform apply
```

## Secrets & Configuration

Required GitHub Secrets:

- `DOCKERHUB_USERNAME` - DockerHub registry username
- `DOCKERHUB_TOKEN` - DockerHub registry access token
- `TOKEN` - GitHub personal access token for automated commits

## Educational Content

The platform teaches:

- **DevOps Zero to Hero** series
- **AWS Zero to Hero**
- **Azure Zero to Hero**
- **Terraform Zero to Hero**
- **Python Zero to Hero**
- **Ansible Zero to Hero**
- **GitOps Zero to Hero**
- **Networking Fundamentals**
- **Kubernetes Troubleshooting**

## Contributing

1. Create a feature branch
2. Make your changes
3. Push to main branch
4. CI/CD pipeline automatically tests and deploys

## License

See LICENSE file for details.

## Contact

For questions or issues, please use the Contact page on the application.

---

**Author**: Vihari Reddy (@Viho-Kernel)  
**Last Updated**: April 21, 2026
