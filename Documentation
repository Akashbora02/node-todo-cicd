# 3-Tier Application Deployment Using Jenkins and Docker

## Project Overview

This project demonstrates the deployment of a 3-tier Todo List application using Jenkins for CI/CD and Docker for containerization. The objective was to automate the application deployment process by integrating GitHub with Jenkins and running the application inside Docker containers.

---

## Architecture

```text
Developer
    |
    v
GitHub Repository
    |
    v
Jenkins Pipeline
    |
    v
Docker Build & Deployment
    |
    v
Todo Application
```

### Components

* **Frontend:** User Interface for managing Todo tasks
* **Backend:** Application logic and API services
* **Database:** Stores Todo task information
* **Jenkins:** Continuous Integration and Deployment
* **Docker & Docker Compose:** Containerization and orchestration

---

## Infrastructure Configuration

| Component              | Configuration    |
| ---------------------- | ---------------- |
| Operating System       | Ubuntu 24.04 LTS |
| CPU                    | 2 vCPUs          |
| Memory                 | 4 GB RAM         |
| Storage                | 20 GB Disk       |
| CI/CD Tool             | Jenkins          |
| Container Platform     | Docker           |
| Source Code Repository | GitHub           |

---

## Deployment Steps

### Step 1: Provision Jenkins Server

Created an Ubuntu virtual machine with the following specifications:

* Ubuntu 24.04 LTS
* 2 vCPUs
* 4 GB RAM
* 20 GB Storage

---

### Step 2: Install Required Dependencies

Installed the following tools on the Jenkins server:

* Java (OpenJDK)
* Jenkins
* Docker
* Docker Compose
* Git

Verified installation and ensured all services were running successfully.

---

### Step 3: Configure Network Access

Updated the security group/firewall rules to allow:

| Port | Purpose            |
| ---- | ------------------ |
| 22   | SSH Access         |
| 8080 | Jenkins Dashboard  |
| 8000 | Application Access |

---

### Step 4: Access Jenkins

Accessed Jenkins using:

```bash
http://<public-ip>:8080
```

Completed the initial Jenkins setup and installed the required plugins.

---

### Step 5: Configure Jenkins Pipeline

Created a Jenkins Pipeline job and configured Source Code Management (SCM) to connect with the GitHub repository.

Pipeline workflow:

1. Fetch source code from GitHub
2. Read Jenkinsfile from repository
3. Build Docker image using Dockerfile
4. Deploy containers using Docker Compose
5. Verify application deployment

---

### Step 6: CI/CD Execution

The Jenkins pipeline automatically executed the deployment process using:

* Dockerfile for image creation
* Docker Compose for container orchestration
* Jenkinsfile for CI/CD automation

This enabled automated application deployment directly from the GitHub repository.

---

## Challenges Faced

### Docker Permission Issue

#### Problem

Jenkins was unable to communicate with the Docker daemon and produced the following error:

```bash
permission denied while trying to connect to the Docker daemon socket
```

#### Resolution

Added the Jenkins user to the Docker group:

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
sudo systemctl restart docker
```

This allowed Jenkins to execute Docker commands successfully.

---

### Application Accessibility Issue

#### Problem

The application was deployed successfully but was not accessible from the browser.

#### Resolution

The application was running on port 8000, which was not open in the security group.

Opened port 8000 in the server security group/firewall settings and verified connectivity.

After updating the rules, the application became accessible externally.

---

## Result

Successfully deployed a 3-tier Todo List application using Jenkins and Docker.

### Key Achievements

* Automated deployment using Jenkins Pipeline
* Integrated GitHub with Jenkins for CI/CD
* Containerized application using Docker
* Managed services using Docker Compose
* Resolved Docker permission and networking issues
* Successfully exposed and accessed the application through the browser

The application is now deployed and can be used to create, update, and manage Todo tasks through a web interface.

---

## Skills Demonstrated

* Linux Administration
* Jenkins CI/CD
* Docker
* Docker Compose
* Git & GitHub
* Application Deployment
* Troubleshooting
* Networking & Security Groups
* DevOps Practices
