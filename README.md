
# 💡 Full-Stack DevOps: Flask Microservice CI/CD Pipeline

> **Building a production-grade CI/CD pipeline for a containerized Flask application using Docker, Jenkins, and GitHub.**

![Last Commit](https://img.shields.io/badge/last%20update-today-success)
![Python](https://img.shields.io/badge/codebase-85.4%25%20Python-blue)
![Languages](https://img.shields.io/badge/languages-2-informational)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Docker](https://img.shields.io/badge/container-Docker-blue)

---

## 📌 Project Overview

This project demonstrates a **professional-grade DevOps pipeline** for deploying a Python-based microservice using Flask. It incorporates:

- Automated builds and testing
- Docker-based deployment
- CI/CD with Jenkins
- Health monitoring and logs

Designed for teams seeking **reliable, scalable, and repeatable deployments**.

---

## 🛠️ Tech Stack & Tools

| Category             | Tool/Service     |
|----------------------|------------------|
| Language             | Python, Flask    |
| Version Control      | Git + GitHub     |
| Containerization     | Docker           |
| CI/CD                | Jenkins          |
| Testing              | Pytest           |
| Monitoring & Logging | Custom Endpoints |

---

## 🗂️ Repo Structure

```bash
DevOps-CICD-Flask-App-Project/
├── app.py                  # Main Flask app
├── Dockerfile              # Docker image build file
├── requirements.txt        # Python dependencies
├── test_app.py             # Unit tests
├── Jenkinsfile             # CI/CD pipeline config (optional)
└── README.md               # You're reading this!
```

---

## ⚙️ Prerequisites

Ensure the following tools are installed and accessible:

- ✅ Python 3.x
- ✅ pip
- ✅ Docker
- ✅ Jenkins (running locally or on server)
- ✅ Git

---

## 📥 Clone & Build Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Harshwardhanjadhav0/DevOps-CICD-Flask-App-Project.git
cd DevOps-CICD-Flask-App-Project
```

### 2. Build Docker Image

```bash
docker build -t flaskapp-cicd .
```

---

## 🚀 Run the Application

### 🔧 Local Python Environment (No Docker)

```bash
pip install -r requirements.txt
python app.py
```

Access the app at: `http://localhost:5000`

### 🐳 Dockerized Execution

```bash
docker run -p 5000:5000 flaskapp-cicd
```

---

## 🌐 API Endpoints

| Endpoint     | Functionality           |
|--------------|-------------------------|
| `/`          | Root Hello World route  |
| `/health`    | App health check        |
| `/metrics`   | Performance metrics     |
| `/logs`      | View application logs   |

---

## 🔁 CI/CD with Jenkins

> This section outlines how Jenkins automates the pipeline.

### Jenkins Setup Steps

1. Install Jenkins on local/remote server
2. Install required plugins: Git, Docker Pipeline
3. Create a new Jenkins job (Freestyle or Pipeline)
4. Add GitHub repository in job configuration
5. Add shell steps:

```bash
docker build -t flaskapp-cicd .
docker run -d -p 5000:5000 flaskapp-cicd
```

Or use a `Jenkinsfile` for full pipeline control.

---

## ✅ Testing

### Local Unit Tests

```bash
pytest test_app.py
```

### Inside Docker (if supported):

```bash
# Replace <container_id> with the actual ID
docker exec <container_id> pytest
```

---

## 🧰 Troubleshooting Tips

| Issue                                | Fix                                                   |
|--------------------------------------|--------------------------------------------------------|
| Docker build failure                 | Check `Dockerfile` syntax & base image availability    |
| Jenkins can't access Docker socket   | Add Jenkins to Docker group (`sudo usermod -aG docker jenkins`) |
| App port not accessible              | Verify EC2 security group or local firewall rules      |
| Pytest fails                         | Check for missing dependencies or misnamed functions   |

---

## 📌 DevOps Best Practices Followed

- ✅ Separation of concerns (code, config, deployment)
- ✅ Automated builds and testing
- ✅ Portability using containers
- ✅ CI/CD as code (optional Jenkinsfile)
- ✅ Health monitoring endpoints

---

## 🧪 Sample Output Screenshot (Local)

> Add screenshots here for visual verification.

```
GET / -> Hello from Flask!
GET /health -> {'status': 'UP'}
GET /metrics -> {'uptime': '123s', 'requests': 18}
GET /logs -> log dump...
```

---

## 🙌 Contributing

Feel free to fork this repo, raise PRs, or open issues. Suggestions welcome!

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` file for details.

---

## 🏁 Final Words

🔧 Built for real-world DevOps practice

🚀 Ready to scale and integrate

💬 Reach out for collaboration or improvements!
Author: Harshwardhan Jadhav