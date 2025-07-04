# Dockerized HTML5UP Site with GitHub Actions CI/CD

This project demonstrates how to containerize a static HTML5UP template using Docker, and automate Docker image builds and pushes using GitHub Actions.

## 🚀 Features
- Static site served with Nginx in Docker
- GitHub Actions workflow to build & push Docker image
- Docker Hub integration for image publishing

## 🛠️ Project Structure
```
├── .github
│   └── workflows
│       └── docker-build.yml     # GitHub Actions workflow
├── Dockerfile                   # Defines Nginx-based Docker container
├── index.html                   # Entry HTML from HTML5UP template
├── assets/                      # CSS, JS, and other static files
└── ...
```

## 📦 Getting Started

### 1. Run Locally (without Docker)
```bash
python3 -m http.server 8080
# Visit http://localhost:8080
```

### 2. Build and Run with Docker
```bash
docker build -t html5up-site .
docker run -d -p 8080:80 html5up-site
# Visit http://localhost:8080
```

### 3. GitHub Actions Workflow
On every push to `main`, GitHub:
- Builds Docker image from `Dockerfile`
- Logs into Docker Hub using secrets
- Pushes image as `DOCKER_USERNAME/html5up-site:latest`

Secrets needed in GitHub:
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD` (or Docker Hub access token)

## 🔗 Links
- [Docker Hub](https://hub.docker.com)
- [HTML5UP Templates](https://html5up.net)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)