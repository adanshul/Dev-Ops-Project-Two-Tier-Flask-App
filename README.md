# Automated CI/CD Pipeline for a 2-Tier Flask Application on AWS

## Project Overview

This project demonstrates an **end-to-end CI/CD pipeline** for a **2-tier web application** built with **Flask and MySQL**, deployed on an **AWS EC2 instance** using **Docker, Docker Compose, and Jenkins**.

The primary goal of this project is to **learn and practice DevOps concepts** by automating the build and deployment process whenever code is pushed to a GitHub repository.

---

## What I Learned from This Project

- Building a complete **CI/CD pipeline using Jenkins**
- Containerizing applications using **Docker**
- Managing multi-container applications with **Docker Compose**
- Automating deployments on **AWS EC2**
- Writing **Pipeline-as-Code** using a Jenkinsfile
- Understanding real-world DevOps workflows

---

## 🏗️ Architecture Overview

High-level architecture of the project:



---

## 🔄 CI/CD Workflow

1. Developer pushes code to the `main` branch
2. Jenkins pipeline is triggered automatically
3. Jenkins:
   - Clones the GitHub repository
   - Builds the Flask Docker image
   - Deploys the application using Docker Compose
4. Updated application becomes live on AWS EC2

---

## Tech Stack

- **Cloud:** AWS EC2 (Ubuntu 22.04)
- **CI/CD Tool:** Jenkins
- **Containerization:** Docker, Docker Compose
- **Backend Framework:** Flask (Python)
- **Database:** MySQL
- **Version Control:** Git & GitHub

---

## Project Structure

.
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── README.md


---

## 🐳 Docker Configuration

### Dockerfile

- Uses `python:3.9-slim` as the base image
- Installs required system and Python dependencies
- Exposes Flask on port `5000`
- Starts the application using `python app.py`

---

## Docker Compose Configuration

The `docker-compose.yml` file defines two services:

### Services

- **flask**
  - Builds the application image
  - Exposes port `5000`
  - Connects to the MySQL service

- **mysql**
  - Uses the official MySQL image
  - Persists data using Docker volumes
  - Exposes port `3306`

Both services communicate over a shared Docker network.

---

## ⚙️ Jenkins Pipeline

The Jenkins pipeline is defined using a `Jenkinsfile` (Pipeline-as-Code).

### Pipeline Stages

1. **Clone Code**
   - Pulls the latest code from the GitHub repository

2. **Build Docker Image**
   - Builds the Flask application Docker image

3. **Deploy with Docker Compose**
   - Stops existing containers
   - Deploys updated containers in detached mode

This ensures every push to the repository results in an automatic deployment.

---

## How to Run This Project

### Prerequisites

- AWS EC2 instance (Ubuntu 22.04)
- Docker and Docker Compose installed
- Jenkins installed and running
- Required ports opened in the EC2 security group:
  - `22` (SSH)
  - `5000` (Flask)
  - `8080` (Jenkins)

---

### Deployment Steps

1. Configure Jenkins with Docker permissions
2. Create a Jenkins pipeline using the repository
3. Push code to the `main` branch
4. Jenkins automatically builds and deploys the application

---

### Access the Application

- **Flask App:**  
  `http://<EC2_PUBLIC_IP>:5000`

- **Jenkins Dashboard:**  
  `http://<EC2_PUBLIC_IP>:8080`

---

## 📈 Future Enhancements

- Add **NGINX reverse proxy**
- Use **AWS RDS** instead of containerized MySQL
- Implement **GitHub Webhooks**
- Add **Secrets Management**
- Add **Monitoring & Logging** (Prometheus, Grafana)

---

## 📌 Disclaimer

This project was built **for learning and practice purposes**.  
It is inspired by existing DevOps tutorials but implemented independently to understand real-world CI/CD concepts and workflows.

---

## 🙌 Acknowledgements

Thanks to the DevOps community and open-source contributors for providing learning resources and inspiration.

---
