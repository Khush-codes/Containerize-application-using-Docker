1. Project Overview

This project is a DevOps assessment consisting of a React frontend and a Django backend. The goal of this assignment is to containerize the application using Docker, automate builds using GitHub Actions, and deploy it on AWS using Terraform.

Tech Stack

Frontend: React

Backend: Django (Python)

Containerization: Docker & Docker Compose

Cloud: AWS EC2

IaC: Terraform

CI/CD: GitHub Actions

2. Local Setup (Docker – Working)
Prerequisites

Git

Docker

Docker Compose

Steps to Run Locally
git clone https://github.com/Khush-codes/Containerize-application-using-Docker

cd Containerize-application-using-Docker
docker compose build
docker compose up -d
Local Access URLs

Frontend: http://localhost:5173

Backend (Admin): http://localhost:8000/admin/

✅ Status: Application works correctly in local Docker setup.

3. AWS EC2 Deployment
EC2 Configuration

OS: Ubuntu

Instance Type: t2.micro

Region: ap-south-1 (Mumbai)

Security Group – Inbound Rules

SSH: 22

Frontend: 5173

Backend: 8000

HTTP: 80

Deployment Steps on EC2
sudo apt update
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu
newgrp docker


git clone https://github.com/Khush-codes/Containerize-application-using-Docker

cd Containerize-application-using-Docker
docker compose up -d
4. CI/CD Pipeline (GitHub Actions)

GitHub Actions is used to automate the build process.

Pipeline Features

Triggered on every push

Builds Docker images

Ensures project structure consistency

Workflow Location

.github/workflows/

5. Infrastructure Using Terraform

Terraform is used to provision AWS infrastructure.

Terraform Resources

EC2 Instance

Custom VPC

Subnet

Internet Gateway

Route Table

Security Group

Terraform Files

main.tf

variables.tf

terraform.tfvars (ignored using .gitignore)

6. Issues & Troubleshooting Log
Issue: Public IP Not Reachable
Problem Description

The application runs correctly in local Docker environment. Docker containers are running on EC2 and ports are exposed. However, the application is not accessible using the EC2 public IP.

Errors Observed

Frontend: ERR_CONNECTION_TIMED_OUT

Backend: ERR_CONNECTION_REFUSED

Troubleshooting Steps Performed

Verified Docker containers using docker ps

Verified port mapping (5173 and 8000)

Checked AWS Security Group inbound rules

Verified UFW firewall status (inactive)

Verified backend accessibility via localhost on EC2

Current Status

Due to time and system constraints, this issue could not be fully resolved. All major DevOps tasks such as Dockerization, CI/CD pipeline, and Terraform-based infrastructure setup were completed successfully.

7. Submission Details

GitHub Repository: https://github.com/Khush-codes/Containerize-application-using-Docker

Deployed URL: Not reachable due to deployment/network issue (documented below)


Final Note

This documentation explains the complete DevOps workflow implemented for the assignment. All steps, configurations, and issues have been documented transparently as per the requirements.