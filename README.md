# MCP GitHub Demo

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green.svg)](https://fastapi.tiangolo.com/)
[![Docker](https://img.shields.io/badge/Docker-Compose-orange.svg)](https://www.docker.com/)

A **demo MCP (Model Context Protocol) server** built with **FastAPI** and **Docker**, integrated with the **GitHub API** to fetch repository data and expose it via an AI-agent-friendly endpoint.  
Includes **Nginx reverse proxy** and **Docker Compose** setup for easy deployment on local or cloud (like EC2).

---

## 📌 Features
- **FastAPI-based** MCP server
- **GitHub API integration** (fetches public repos)
- **Reverse proxy** using Nginx (`/github` endpoint)
- **Docker & Docker Compose** for quick setup
- Ready for **AI agent consumption**

---

## 🛠 Prerequisites
- [Docker](https://docs.docker.com/get-docker/) installed
- [Docker Compose](https://docs.docker.com/compose/) installed
- (Optional) GitHub personal access token for private repos

---

## 🚀 Setup & Run

```bash
# Clone this repo
git clone https://github.com/<your-username>/mcp-github-demo.git
cd mcp-github-demo

# Build and run containers
docker-compose up --build
```

---

## 🔍 Test Endpoints

**List Octocat repositories:**
```
http://localhost/github?user=octocat
```

**List your repositories:**
```
http://localhost/github?user=<your_github_username>
```

**Sample Response**
```json
{
  "service": "MCP-GitHub",
  "repos": ["repo1", "repo2", "repo3"]
}
```

---

## 🛑 Stop Services

```bash
docker-compose down
```

---

## 📖 How It Works

1. **FastAPI** handles `/` requests and calls GitHub API.
2. **Nginx** reverse proxies `/github` requests to the FastAPI container.
3. **AI Agents** or other apps call `http://<server>/github?user=username` to get structured JSON.

---

## 🔮 Future Scope

- Add more MCP servers (Jira, Y-Finance, etc.)
- Secure endpoints (Auth tokens)
- Deploy to AWS ECS/EKS

---

## 🧑‍💻 Author

**Roshan Kumar Singh**

- [LinkedIn](#)
- [YouTube](#)

---

## 📄 License

This project is licensed under the MIT License.
