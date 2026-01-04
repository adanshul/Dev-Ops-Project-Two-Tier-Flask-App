🚀 Automated CI/CD Pipeline for a 2-Tier Flask Application on AWS
📌 Project Overview

This project demonstrates an end-to-end CI/CD pipeline for a 2-tier web application built with Flask and MySQL, deployed on AWS EC2 using Docker, Docker Compose, and Jenkins.

The goal of this project is to learn and practice DevOps fundamentals by automating the build and deployment process whenever code is pushed to GitHub.

🧠 What I Learned from This Project

Setting up a Jenkins CI/CD pipeline from scratch

Containerizing applications using Docker

Managing multi-container apps with Docker Compose

Automating deployments on AWS EC2

Writing Pipeline-as-Code using a Jenkinsfile

🏗️ Architecture Overview

High-level flow:

Developer → GitHub → Jenkins (CI/CD) → Docker → AWS EC2


Components:

Flask Application – Backend web service

MySQL Database – Persistent data storage

Jenkins – CI/CD automation server

Docker & Docker Compose – Containerization and orchestration

AWS EC2 – Deployment infrastructure

🔄 CI/CD Workflow

Developer pushes code to the main branch

Jenkins automatically:

Clones the GitHub repository

Builds Docker images

Deploys containers using Docker Compose

Updated application goes live on the EC2 instance

🧰 Tech Stack

Cloud: AWS EC2 (Ubuntu 22.04)

CI/CD: Jenkins

Containers: Docker, Docker Compose

Backend: Flask (Python)

Database: MySQL

Version Control: GitHub

📂 Repository Structure
.
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── README.md

🐳 Docker & Containerization
Dockerfile

Uses python:3.9-slim

Installs dependencies

Exposes Flask on port 5000

docker-compose.yml

Defines two services:

flask – Application container

mysql – Database container

Uses a shared Docker network

Persists database data using volumes

⚙️ Jenkins Pipeline (Jenkinsfile)

The pipeline consists of three main stages:

Clone Code – Pulls the latest code from GitHub

Build Image – Builds the Flask Docker image

Deploy – Runs containers using Docker Compose

This ensures every code change is automatically deployed.

🚀 How to Run This Project
Prerequisites

AWS EC2 instance (Ubuntu)

Docker & Docker Compose installed

Jenkins installed and running

Ports opened: 22, 5000, 8080

Deployment

Once Jenkins is configured:

Push code to the main branch

Jenkins will automatically deploy the application

Access

Flask App: http://<EC2_PUBLIC_IP>:5000

Jenkins Dashboard: http://<EC2_PUBLIC_IP>:8080

📈 Future Improvements

Use environment variables / secrets management

Add NGINX reverse proxy

Use AWS RDS instead of containerized MySQL

Implement GitHub Webhooks

Add monitoring (Prometheus + Grafana)