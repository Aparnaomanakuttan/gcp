# Student management system

This system is mainly for managing studnet data. It consists of a frontend for user interaction and a backend for processing and storing data in a PostgreSQL database. The application is containerized using Docker and deployed using Kubernetes.


## Getting Started

### Prerequisites

- Docker
- Kubernetes (GCP, GKE, or other Kubernetes platforms)
- Git
- PostgreSQL

### Setup Instructions

1. *Clone the repository:*

   ```bash
   git clone <repository_URL>
   cd <repository_name>
# Building Docker Images 
# Frontend
cd frontend
docker build -t frontend-app .

# Backend
cd ../backend
docker build -t backend-app .

#Pushing to registery
docker tag frontend-app <your_registry>/frontend-app:v1
docker push <your_registry>/frontend-app:v1

docker tag backend-app <your_registry>/backend-app:v1
docker push <your_registry>/backend-app:v1

#Deploymwnt
kubectl apply -f deployment/backend-deployment.yaml
kubectl apply -f deployment/backend-service.yaml

kubectl apply -f deployment/frontend-deployment.yaml
kubectl apply -f deployment/frontend-service.yaml

Access the Application
Once deployed, you can access the frontend service using the Load Balancer IP or node port provided by Kubernetes. The frontend interacts with the backend to submit and retrieve student information.

Development Workflow
Branching and Pull Requests
Create a new branch for features or bug fixes:

bash
Copy code
git checkout -b feature/new-feature
Work on your changes and commit them with meaningful messages:

bash
Copy code
git add .
git commit -m "Add feature XYZ"
Push your branch to GitHub:

bash
Copy code
git push origin feature/new-feature
Create a pull request on GitHub:

Go to your repository on GitHub.
Click on the "Pull requests" tab.
Click "New pull request" and select your branch.
Provide a descriptive title and description.
Submit the pull request.
Review and merge:

Team members review the pull request.
Once approved, merge the changes into the main branch.
