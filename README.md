# Internal DevOps Utilities API

## Aim

Internal API surface for common DevOps utilities, intended for internal teams:

- AWS Resources APIs
- Metrics
- Log Analysis

---

# Usage

```bash
git clone <repo-url>
cd devops-utilities-api
```

---

## Setup Python Environment

```bash
python3.14 -m venv venv
source venv/bin/activate
```

---

## Install Requirements

```bash
pip install -r requirements.txt
```

---

## Run Application

```bash
python main.py
```

---

# 🐳 Docker Setup (NEW)

## Build Docker Image

```bash
docker build -t devops-utilities-api .
```

---

## Run Docker Container

```bash
docker run -p 8000:8000 devops-utilities-api
```

---

# 🐳 Dockerfile

```dockerfile
FROM python:3.14

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 8000

CMD ["python","main.py"]
```

---

# ☁️ AWS EC2 Deployment

After Dockerizing the application:

- Created AWS EC2 Linux Instance
- Installed Docker CLI on EC2
- Built Docker image on server
- Ran containerized FastAPI application
- Exposed application on Port 8000
- Accessed APIs remotely using EC2 Public IP

This converted the project from a local development backend into a cloud-hosted production-style DevOps utility API.

---

# Internal DevOps Utilities API using FastAPI, Python, Docker & AWS

---

# 🟦 Situation (Problem / Idea)

In real-world DevOps and infrastructure environments, engineers frequently perform repetitive operational tasks such as:

* checking system metrics,
* monitoring CPU/memory usage,
* analyzing infrastructure health,
* and tracking AWS resources manually.

These operations are often distributed across multiple tools, dashboards, and AWS consoles, making monitoring and troubleshooting time-consuming.

I wanted to understand how internal DevOps utility platforms are designed in production environments and how backend APIs can centralize operational monitoring workflows.

The idea was to build a centralized Internal DevOps Utilities API that could expose system monitoring and AWS utility operations through scalable REST APIs.

Additionally, I wanted to simulate real-world production deployment practices used by DevOps teams.  
So I enhanced the project using Docker containerization and deployed it on AWS EC2.

---

# 🟦 Task (Goal / Responsibility)

My task was to design and develop a modular DevOps utility backend API capable of:

* monitoring real-time system metrics,
* exposing infrastructure utility endpoints,
* integrating AWS services,
* analyzing S3 bucket information,
* following scalable API architecture practices,
* containerizing the application using Docker,
* and deploying the application on AWS EC2.

The goal was to:

* reduce repetitive manual monitoring tasks,
* centralize operational utilities,
* simulate real-world DevOps backend utility systems,
* and understand production deployment workflows.

---

# 🟦 Action (Actual Implementation / Technologies Used)

I implemented the project using:

- Python
- FastAPI
- Uvicorn
- psutil
- AWS Boto3 SDK
- Docker
- AWS EC2

---

# 🔹 Core Implementation

## ✅ API Architecture

Designed modular FastAPI backend architecture using:

* `routers/`
  → API route handling

* `services/`
  → business logic layer

* `app/api.py`
  → centralized FastAPI application initialization

* `main.py`
  → application entry point using Uvicorn ASGI server

This structure follows scalable backend architecture practices used in production systems.

---

## ✅ FastAPI REST API Development

Implemented multiple REST API endpoints including:

* `/`
  → Health/Test endpoint

* `/metrics`
  → system monitoring endpoint

* `/aws/s3`
  → AWS S3 bucket analysis endpoint

* `/aws/ec2`
  → placeholder endpoint for future EC2 utility integration

Used:

* FastAPI routing
* APIRouter
* JSON responses
* HTTP status handling

---

## ✅ System Metrics Monitoring

Integrated `psutil` library for real-time system monitoring.

Collected:

* CPU usage
* memory utilization
* disk usage

Implemented:

* configurable CPU threshold monitoring
* system health classification

Example:

* CPU > threshold
  → “High CPU”
* otherwise
  → “Healthy”

This simulates infrastructure monitoring concepts used in DevOps and SRE environments.

---

## ✅ AWS S3 Integration

Integrated AWS S3 services using Boto3 SDK.

Implemented:

* S3 bucket listing
* bucket age analysis
* classification of buckets into:

  * new buckets
  * old buckets

Logic:

* buckets older than 90 days categorized as old buckets.

Used:

* timezone-aware datetime handling
* timedelta-based age calculation

This simulates cloud governance and AWS resource analysis workflows.

---

## ✅ Docker Containerization (NEW ADDITION)

To make the application production-ready and portable, I containerized the FastAPI application using Docker.

Created a custom Dockerfile to:

* package the application with all dependencies,
* eliminate environment dependency issues,
* ensure same behavior across systems,
* simplify deployment process,
* and support scalable DevOps deployment workflows.

Docker helped in running the project consistently across local systems and cloud servers without manual dependency setup.

This follows real-world DevOps deployment standards used in production environments.

---

## ✅ AWS EC2 Deployment

After Dockerizing the application:

* created AWS EC2 Linux instance,
* installed Docker CLI on EC2,
* built Docker image,
* ran containerized FastAPI application,
* exposed application using Port 8000,
* and hosted the backend API on cloud infrastructure.

This gave practical understanding of:

* cloud deployment,
* server configuration,
* container execution,
* networking,
* and production-style backend hosting.

---

## ✅ Error Handling & API Reliability

Implemented:

* exception handling
* HTTP status codes
* internal server error responses

Used:

* `HTTPException`
* status code management
* structured JSON error responses

This improved API reliability and production-readiness.

---

# 🔹 Technologies & Tools Used

* Python
* FastAPI
* Uvicorn
* AWS Boto3
* psutil
* Docker
* AWS EC2
* REST APIs
* AWS S3
* JSON APIs
* DevOps Monitoring
* Infrastructure Monitoring
* Backend API Architecture
* Containerization
* Cloud Deployment

---

# 🔹 Challenges Solved

During development, I worked on:

* modular API architecture design
* AWS SDK integration
* real-time system metric collection
* API routing structure
* exception handling
* timezone-aware bucket age calculations
* scalable backend organization using routers and services
* Docker containerization
* EC2 deployment setup
* application hosting on cloud infrastructure

---

# 🟦 Result (Outcome / Quantifiable Impact)

* Successfully developed and deployed a modular Internal DevOps Utilities API for infrastructure monitoring and AWS utilities.

* Automated 4+ operational utility workflows including:

  * system metrics monitoring,
  * CPU health analysis,
  * AWS S3 bucket analysis,
  * infrastructure utility API exposure,
  * and containerized deployment workflows.

* Built reusable and scalable REST API architecture using FastAPI routers and service layers.

* Successfully Dockerized the application and deployed it on AWS EC2 cloud server.

* Improved understanding of:

  * backend API development,
  * DevOps monitoring workflows,
  * AWS integrations,
  * infrastructure health analysis,
  * Docker containerization,
  * cloud deployment,
  * and production-style backend architecture.

* Gained hands-on experience in:

  * FastAPI,
  * REST API development,
  * AWS Boto3,
  * Docker,
  * AWS EC2,
  * infrastructure monitoring,
  * backend modular architecture,
  * and DevOps utility automation.

---

# BEST INTERVIEW EXPLANATION

“This project is a modular Internal DevOps Utilities API developed using Python, FastAPI, psutil, AWS Boto3 SDK, Docker, and AWS EC2.

The main goal was to centralize DevOps operational utilities such as system monitoring and AWS resource analysis through REST APIs.

I implemented modular backend architecture using routers and services, integrated psutil for real-time CPU, memory, and disk monitoring, and used Boto3 to analyze AWS S3 bucket information.

To make the project production-ready, I containerized the application using Docker and deployed it on AWS EC2 cloud infrastructure.

I also implemented exception handling, status management, and scalable API organization similar to production backend systems.

Through this project, I gained practical understanding of FastAPI backend development, infrastructure monitoring, AWS integrations, Docker containerization, cloud deployment, and DevOps automation workflows.”

---

# ATS-Friendly Resume / LinkedIn Description

🔹 Developed a modular Internal DevOps Utilities API using Python, FastAPI, psutil, Docker, and AWS Boto3 SDK to automate infrastructure monitoring and AWS utility workflows.

🔹 Implemented 4+ REST API endpoints for real-time system metrics monitoring, CPU health analysis, AWS S3 bucket analysis, and infrastructure utility operations.

🔹 Integrated psutil for CPU, memory, and disk usage monitoring with configurable threshold-based system health classification.

🔹 Integrated AWS S3 services using Boto3 SDK and implemented automated bucket analysis workflows including bucket age classification and cloud resource monitoring.

🔹 Designed scalable backend architecture using FastAPI routers and service layers with structured exception handling and JSON-based API responses.

🔹 Containerized the FastAPI application using Docker and deployed it on AWS EC2 cloud server for production-style backend hosting.

🔹 Gained hands-on experience in FastAPI, REST APIs, Docker, AWS EC2, AWS integrations, infrastructure monitoring, backend architecture, DevOps workflows, and cloud automation.

---

# How to Explain Architecture to Interviewer

Client Request  
      ↓  
FastAPI Router Layer  
      ↓  
Service Layer (Business Logic)  
      ↓  
AWS / System Utilities  
      ↓  
JSON API Response

---

# Simple Understanding of Folder Structure

main.py  
↓  
Starts FastAPI Server

app/api.py  
↓  
Creates FastAPI Application

routers/  
↓  
Handles API Endpoints

services/  
↓  
Contains Actual Business Logic

Dockerfile  
↓  
Containerizes Application for Deployment

AWS EC2  
↓  
Hosts Application on Cloud Server

---

# BEST INTERVIEW CLOSING LINE

“This project helped me understand how production-style backend APIs are designed for DevOps monitoring, infrastructure automation, Docker containerization, cloud deployment, and AWS operational utilities using modular FastAPI architecture.”
