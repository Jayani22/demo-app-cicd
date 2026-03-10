# CI/CD Pipeline with GitHub Actions, Docker and EC2

## Project Overview
This project demonstrates a CI/CD pipeline that automatically builds, pushes, and deploys a Dockerized application using GitHub Actions.

Whenever code is pushed to the GitHub repository, a new Docker image is built and pushed to Docker Hub. The deployment workflow then connects to an EC2 instance and redeploys the application automatically using Docker Compose.

## Technologies Used

- GitHub Actions
- Docker
- Docker Hub
- AWS EC2
- Docker Compose
- Nginx (for serving the demo app)

## CI/CD Workflow

### Continuous Integration (CI)

Triggered on every push to the main branch.

Steps:
1. Checkout the source code
2. Build a Docker image from the Dockerfile
3. Tag the image using the commit SHA
4. Push the image to Docker Hub

### Continuous Deployment (CD)

Triggered after the CI workflow completes.

Steps:
1. Connect to the EC2 instance using SSH
2. Install Docker and Docker Compose if not already installed
3. Create or update the docker-compose.yml file
4. Pull the latest Docker image from Docker Hub
5. Restart the container using Docker Compose

## Deployment Verification

After deployment, the application can be accessed via the EC2 public IP address.

Example:

http://EC2_PUBLIC_IP

## Author

DevOps Internship Task