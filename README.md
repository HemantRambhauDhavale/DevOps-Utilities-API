# Internal DevOps Utilities API

## Aim

Internal API surface for common DevOps utilities, intended for internal teams:

- AWS Resources APIs
- Metrics
- Log Analysis

## Usage

```bash
git clone <repo-url>
cd devops-utilities-api
```

### setup python environment
```bash
python3.14 -m venv venv
source venv/bin/activate
```

### install requirements
```bash
pip install -r requirements.txt
```

### run application
```bash
python main.py
```

# Internal DevOps Utilities API using FastAPI, Python & AWS

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

---

# 🟦 Task (Goal / Responsibility)

My task was to design and develop a modular DevOps utility backend API capable of:

* monitoring real-time system metrics,
* exposing infrastructure utility endpoints,
* integrating AWS services,
* analyzing S3 bucket information,
* and following scalable API architecture practices.

The goal was to:

* reduce repetitive manual monitoring tasks,
* centralize operational utilities,
* and simulate real-world DevOps backend utility systems.

---

# 🟦 Action (Actual Implementation / Technologies Used)

I implemented the project using Python, FastAPI, psutil, and AWS Boto3 SDK.

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
* REST APIs
* AWS S3
* JSON APIs
* DevOps Monitoring
* Infrastructure Monitoring
* Backend API Architecture

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

---

# 🟦 Result (Outcome / Quantifiable Impact)

* Successfully developed a modular Internal DevOps Utilities API for infrastructure monitoring and AWS utilities.

* Automated 4+ operational utility workflows including:

  * system metrics monitoring,
  * CPU health analysis,
  * AWS S3 bucket analysis,
  * and infrastructure utility API exposure.

* Built reusable and scalable REST API architecture using FastAPI routers and service layers.

* Improved understanding of:

  * backend API development,
  * DevOps monitoring workflows,
  * AWS integrations,
  * infrastructure health analysis,
  * and production-style backend architecture.

* Gained hands-on experience in:

  * FastAPI,
  * REST API development,
  * AWS Boto3,
  * infrastructure monitoring,
  * backend modular architecture,
  * and DevOps utility automation.

---

# 🎯 BEST INTERVIEW EXPLANATION

“This project is a modular Internal DevOps Utilities API developed using Python, FastAPI, psutil, and AWS Boto3 SDK.

The main goal was to centralize DevOps operational utilities such as system monitoring and AWS resource analysis through REST APIs.

I implemented modular backend architecture using routers and services, integrated psutil for real-time CPU, memory, and disk monitoring, and used Boto3 to analyze AWS S3 bucket information.

I also implemented exception handling, status management, and scalable API organization similar to production backend systems.

Through this project, I gained practical understanding of FastAPI backend development, infrastructure monitoring, AWS integrations, and DevOps automation workflows.”
