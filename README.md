CloudOps Portfolio — Deploying a Web App with Docker & Kubernetes

Project Overview

This project demonstrates how to package and deploy a simple web application using Docker and Kubernetes.

The project covers containerization, Kubernetes Deployment, Service networking, health checks, and local application access.

Technologies Used

* Docker — builds the application container image.
* Kubernetes — manages application Pods and Deployment.
* Kubernetes Deployment — runs two application replicas.
* Kubernetes Service (NodePort) — exposes the application through port 30080.
* HTML, CSS, JavaScript — provides the portfolio web interface.

Architecture

User / Web Browser
        |
        v
Localhost:8082
        |
        v
kubectl port-forward
        |
        v
Kubernetes Service
        |
        v
Kubernetes Deployment
        |
        v
Application Pods (2 replicas)
        |
        v
Docker Container

Project Structure

PORTFOLIO-DOCKER-K8S/
├── index.html
├── dockerfile
├── deployment.yaml
├── service.yaml
└── README.md

Kubernetes Configuration

The Deployment is configured to run two replicas of the application.

The Service uses NodePort with port 30080 and forwards traffic to application port 80.

Readiness and liveness probes are configured to check application health.

Run the Application Locally

Make sure Docker and your Kubernetes cluster are running.

Apply the Kubernetes manifests:

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

Check the Deployment and Pods:

kubectl get deployments
kubectl get pods
kubectl get services

Forward local port 8082 to application port 80:

kubectl port-forward service/cloud-demo-service 8082:80

Open the following address in your browser:

http://localhost:8082

Keep the terminal running while using port-forward.

Skills Demonstrated

* Containerizing a web application with Docker
* Deploying an application on Kubernetes
* Configuring Deployment replicas
* Exposing an application using a Kubernetes Service
* Configuring readiness and liveness probes
* Troubleshooting local port conflicts
* Documenting cloud-native infrastructure

Project Status

The application has been deployed locally and verified through the browser.

This is a learning project running in a local Kubernetes environment. It has not yet been deployed to a public cloud.

Future Improvements

* Publish the project source code on GitHub
* Add automated build and deployment with CI/CD
* Add monitoring and logging
* Deploy to a cloud Kubernetes service

Author

[Andrian]

Aspiring Cloud / DevOps Engineer
