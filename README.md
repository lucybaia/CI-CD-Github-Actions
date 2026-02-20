# 🎡 CI-CD-Github-Actions

This repository automates the Continuous Integration (CI) and Continuous Deployment (CD) pipeline for a Python API. Every push to the `main` branch triggers an automated workflow that builds a Docker image and pushes it to Azure Container Registry (ACR).

---

## 🛠️ Project Components

- **GitHub Actions:** The orchestration engine that runs the automated pipeline.
- **Docker:** Used to containerize the Python application.
- **Azure Container Registry (ACR):** A secure private registry in Azure where the container images are stored.
- **Azure Service Principal:** A secure identity that allows GitHub to authenticate with Azure without using personal passwords.

---

## 🚀 Repository Structure

The repository is organized to allow the GitHub Actions runner to access the build context efficiently:

| Path | Description |
|---|---|
| 📁 `.github/workflows/` | Contains the `main.yml` file which defines the automation logic. |
| 📁 `app/` | Contains the Python application source code (e.g., `main.py`). |
| 📄 `Dockerfile` | Instructions for building the container image. |
| 📄 `README.md` | Project documentation. |

---

## ⚙️ Implementation Steps

### 1. Security & Authentication

A Service Principal was generated in Azure to grant GitHub specific permissions. These credentials were then added as a GitHub Repository Secret named `AZURE_CREDENTIALS` to ensure secure communication between the platforms.

### 2. Workflow Definition

The `.github/workflows/main.yml` file is configured with the following steps:

- **Trigger:** Activated on every `push` to the `main` branch.
- **Environment:** Executes on a hosted `ubuntu-latest` runner.
- **Tasks:**
  1. **Checkout:** Copies the repository code to the runner.
  2. **Azure Login:** Authenticates using the stored secrets.
  3. **Build & Push:** Logs into the ACR, builds the Docker image, and pushes it with a unique tag based on the GitHub run ID.

---

## 📈 Portfolio Summary

> **About:** Automated CI/CD pipeline using GitHub Actions to build and push Docker images to Azure Container Registry. This project implements secure authentication via Service Principals and demonstrates Continuous Integration principles. It is a core part of my Systems Analysis DevOps roadmap and my Academic Monitoring System infrastructure.
