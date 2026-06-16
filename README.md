# Automated CI/CD Pipeline for Java Web Applications

## Project Overview

This project implements an end-to-end Continuous Integration and Continuous Deployment (CI/CD) pipeline for Java web applications using GitHub, Jenkins, Maven, Ansible, Apache Tomcat, Docker, Kubernetes, and AWS EC2. The pipeline automates source code integration, application build, artifact management, deployment, containerization, and orchestration, reducing manual effort and improving deployment reliability.

The workflow begins when developers push code to GitHub. Jenkins, hosted on AWS EC2, automatically retrieves the latest source code, builds the application using Maven, generates a WAR file, and transfers it to the Ansible server. Ansible automates deployment to Apache Tomcat, builds and pushes Docker images to Docker Hub, and deploys the application to a Kubernetes cluster for scalable and reliable application delivery.

---

## Architecture

```text
Developer
    │
    ▼
 GitHub
    │
    ▼
 Jenkins (AWS EC2)
    │
    ▼
 Maven Build
    │
    ▼
 Ansible (AWS EC2)
    │
    ├── Deploy to Apache Tomcat
    │
    └── Build Docker Image
            │
            ▼
       Docker Hub
            │
            ▼
      Kubernetes
```

---

## Workflow

1. Developer pushes source code to GitHub.
2. Jenkins pipeline is triggered automatically.
3. Jenkins checks out the latest source code.
4. Maven builds the application and generates a WAR file.
5. Jenkins archives the build artifact.
6. Jenkins transfers the WAR file to the Ansible server.
7. Ansible deploys the application to Apache Tomcat.
8. Application functionality is verified.
9. Ansible builds a Docker image.
10. Docker image is pushed to Docker Hub.
11. Kubernetes deploys the application using manifest files.
12. Kubernetes manages application deployment and scaling.

---

## Jenkins Pipeline Stages

### Stage 1: Source Code Checkout

* Fetch latest code from GitHub repository.

### Stage 2: Build Application

* Compile source code using Maven.
* Generate WAR artifact.

### Stage 3: Archive Artifact

* Store build artifacts for future reference.

### Stage 4: Transfer Artifact

* Send WAR file to the Ansible server.

### Stage 5: Execute Deployment

* Trigger Ansible playbook execution.

### Stage 6: Containerization

* Build Docker image.
* Push image to Docker Hub.

### Stage 7: Kubernetes Deployment

* Deploy application to Kubernetes cluster.

---

## Ansible Automation Tasks

* Copy WAR file to Tomcat webapps directory.
* Restart Tomcat service.
* Verify application deployment.
* Build Docker image.
* Push Docker image to Docker Hub.
* Apply Kubernetes manifest files.
* Verify Kubernetes deployment status.

---

## Key Features

* Automated CI/CD Pipeline
* Continuous Integration using Jenkins
* Automated Deployment using Ansible
* Docker Containerization
* Kubernetes Orchestration
* CI/CD Infrastructure Hosted on AWS EC2
* Reduced Manual Deployment Effort
* Faster and Reliable Software Delivery

---

## Project Outcome

* Automated the complete software delivery lifecycle.
* Improved deployment consistency and reliability.
* Reduced manual intervention through automation.
* Enabled faster release cycles.
* Implemented containerized deployments using Docker and Kubernetes.
* Utilized AWS EC2 instances to host and manage CI/CD infrastructure.
* Established a scalable and repeatable CI/CD process.

---

## Technologies Used

| Technology    | Purpose                               |
| ------------- | ------------------------------------- |
| AWS EC2       | CI/CD Infrastructure Hosting          |
| Git           | Version Control                       |
| GitHub        | Source Code Repository                |
| Jenkins       | CI/CD Automation                      |
| Maven         | Build Automation                      |
| Ansible       | Configuration Management & Deployment |
| Apache Tomcat | Application Server                    |
| Docker        | Containerization                      |
| Docker Hub    | Container Registry                    |
| Kubernetes    | Container Orchestration               |
| Linux         | Server Environment                    |

---

## Author

**Gowtham Degala**

DevOps Engineer | AWS Cloud Engineer

LinkedIn: https://linkedin.com/in/Degala-Gowtham

GitHub: https://github.com/Gowtham-52
