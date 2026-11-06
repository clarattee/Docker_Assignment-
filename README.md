# Full-Stack Application Containerization & Orchestration

A professional DevOps proof-of-concept project demonstrating the containerization, environment isolation, and orchestration of a multi-container full-stack application using **Docker** and **Docker Compose**.

---

## 🏗️ Project Architecture

The application structure consists of two decoupled microservices communicating across an isolated, software-defined internal network bridge managed by Docker Compose:

1. **Frontend (Node.js & Express):** A containerized web server hosting an active user interface form (adapted from the Flask assignment). It captures input fields (`itemName` and `itemDescription`) and dynamically routes an asynchronous JavaScript `fetch` POST payload to the backend API layer.
2. **Backend (Flask):** A Python API backend configured with `flask-cors` cross-origin headers to safely intercept JSON data vectors, log the entry data to the stdout container logging system (`flush=True`), and return structural verification data back to the frontend.

---

## 📂 Repository Structural Tree

```text
Docker_Mohammed Tauseef Asif Shaikh/
│
├── frontend/
│   ├── Dockerfile
│   ├── package.json
│   ├── server.js
│   └── public/
│       └── index.html
│
├── backend/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
│
├── docker-compose.yml
└── .gitignore
```

---

## 🔧 Multi-Container Orchestration (`docker-compose.yml`)

The runtime environment is orchestrated via a unified declaration manifest mapping ports out to the localhost interface layer:
* **Frontend UI Service:** Exposed externally at `http://localhost:3000`
* **Backend API Service:** Exposed externally at `http://localhost:5000`

---

## 🛑 Enterprise Constraints & Virtualization Strategy

Due to corporate compliance group policies on the workstation host machine preventing local installation of **WSL 2 (Windows Subsystem for Linux)** or execution of background hypervisor engines, local containerization was bypassed. 

To achieve exact technical validation, building, image compilation, and orchestration tracking logs were executed inside a cloud-hosted **Linux Container Playground System**.

### Core Execution Pipeline:

```bash
# 1. Compile the custom blueprints and launch the containers in background detached mode
docker compose up --build -d

# 2. Verify network port configurations and active process column status
docker compose ps
```

### Remote Distribution Targets:
* 🌐 **GitHub Codebase Repository:** `https://github.com`
* 📦 **Docker Hub Image Repositories:**
  * Frontend Application: `tauseefclaratte/express-frontend:latest`
  * Backend Application: `tauseefclaratte/flask-backend:latest`

