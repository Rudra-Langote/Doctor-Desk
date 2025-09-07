# Doctor-Desk 🩺

Doctor-Desk is a web application for doctor appointment management, seamlessly deployed on a remote server with CI/CD automation. The project uses Jenkins pipelines, Docker, and Docker Compose for scalable, reliable, and repeatable production deployments.

---

## Features

- **React Frontend**: Modern UI built with Create React App.
- **CI/CD Automation**: Deployments triggered by GitHub push using Jenkins.
- **Containerization**: Efficient multi-stage Docker build, served with Nginx.
- **Orchestration**: Docker Compose manages containers and networking.

---

## Technology Stack

- **Frontend**: React (JavaScript, HTML)
- **Containers**: Docker, Docker Compose
- **Web Server**: Nginx
- **Automation**: Jenkins Pipeline

---

## Deployment Workflow

The Jenkins pipeline automates the following steps:

1. **Clone Repository**: Fetches the latest source code from GitHub.
2. **Build Docker Image**: Uses a multi-stage Dockerfile to build and package the React app in an Nginx container.
3. **Publish Image**: Tags and uploads the final image to Docker Hub.
4. **Run Container**: Initializes the container using docker-compose for easy deployment and updates.

**Sample Jenkins Steps:**
Clone repository from GitHub
git clone https://github.com/Rudra-Langote/Doctor-Desk.git

Build Docker image
docker build -t doctordesk:app .

Tag and push image
docker tag doctordesk:app rudralangote/doctordesk:app
docker push rudralangote/doctordesk:app

Deploy with Docker Compose
docker-compose up -d

---

## Getting Started

### Prerequisites

- Docker & Docker Compose installed
- Jenkins server (optional for manual deployment)
- Node.js (for local development)

### Local Development

Install dependencies
npm install

Start development server
npm start

Visit [http://localhost:3000](http://localhost:3000) to view the app.

### Production Build

npm run build

Generated files are found in the `build/` directory.

---

## Docker Deployment

Build and run the container:

docker build -t doctordesk:app .
docker run -p 80:80 doctordesk:app

Or use Docker Compose:

docker-compose up -d

---

## CI/CD Pipeline (Jenkins)

The Jenkinsfile covers:

- GitHub repo cloning
- Docker image build from Dockerfile
- Push image to Docker Hub
- Start container with Docker Compose

Typical logs include details on cloning, building, pushing, and bringing up containers. Troubleshoot errors using pipeline output.

---

## Troubleshooting

- Ensure Docker, Docker Compose, and Jenkins have adequate permissions.
- Update Node and dependencies to resolve build warnings.
- Consult pipeline logs for diagnostic details.

---

**Contributions and PRs are welcome!**  
Feel free to fork, modify, and deploy Doctor-Desk for your team or organization.
