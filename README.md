# Simple Web Application

This is a simple web application using [Python Flask](http://flask.pocoo.org/) and [MySQL](https://www.mysql.com/) database. 
This is used in the demonstration of the development of Ansible Playbooks.
The project implements a Flask web API that serves as a backend for web applications. 
It provides various endpoints for CRUD operations, enabling developers to easily integrate and utilize its functionalities.

  
  Below are the steps required to get this working on a base linux system.
  
  - **Install all required dependencies**
  - **Install and Configure Web Server**
  - **Start Web Server**
   
## 1. Install all required dependencies
  
  Python and its dependencies
  ```bash
  apt-get install -y python3 python3-setuptools python3-dev build-essential python3-pip default-libmysqlclient-dev
  ```
   
## 2. Install and Configure Web Server

Install Python Flask dependency
```bash
pip3 install flask
pip3 install flask-mysql
```

- Copy `app.py` or download it from a source repository
- Configure database credentials and parameters 



## Project Summary

### API Functionality
- **User Authentication**: Securely authenticate users with JWT tokens.
- **Data Management**: Perform create, read, update, and delete operations on resources.
- **Response Format**: All API responses are returned in JSON format for ease of integration.

### Containerization
The API is containerized using Docker, which allows for easy deployment and scalability. The Dockerfile includes:
- Base image: Python
- Dependencies installation: Using `requirements.txt`
- Command to run the Flask application.

### CI/CD Process
The CI/CD pipeline automates the process of building and deploying the API. It consists of:
1. **Continuous Integration**: 
   - The code is checked out from the repository.
   - Docker Buildx is set up for multi-platform builds.
   - The Docker image is built and pushed to Docker Hub.
   - A security scan using Trivy is performed to check for vulnerabilities.

2. **Continuous Deployment**:
   - The Docker image is deployed to a Kubernetes cluster for production use.

### Deployment on Kubernetes
The API is deployed on a Kubernetes cluster using the following resources:
- **Deployment**: Manages the deployment of the application.
- **Service**: Exposes the API to external traffic.
- **Ingress**: Configures access to the service via HTTP/S.

### Security Measures Implemented
To ensure the security of the API, the following measures are implemented:
- **Environment Variables**: Sensitive data such as database credentials are stored as environment variables.
- **JWT Authentication**: JSON Web Tokens are used for secure authentication.
- **Vulnerability Scanning**: The CI/CD pipeline includes a step to scan the Docker image for vulnerabilities using Trivy.

## Getting Started
To get started with the Flask Web API, clone the repository and run the following commands:

```bash
# Clone the repository
git clone https://github.com/<your-username>/flask-web-app.git

# Navigate to the project directory
cd flask-web-app

# Build and run the Docker container
docker-compose up --build


Open a browser and go to URL
```
http://<IP>:8080                            => Welcome
http://<IP>:5000/how%20are%20you            => I am good, how about you?
```

## Start Web Server

Start web server
```bash
FLASK_APP=app.py flask run --host=0.0.0.0
```

## Test

#Specifically for Flask Web API
