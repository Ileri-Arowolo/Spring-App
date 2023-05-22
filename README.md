# Spring-App
## Jenkins - Docker - Kubernetes Integration for Banking Client

This documentation provides instructions on deploying a multi-tier application using Jenkins, Docker, and Kubernetes for a banking client.

### Development Workflow

1. Developers write and commit code to our GitHub source code management.
2. Before committing code, developers perform unit tests.
3. Source code, test cases, and build scripts are prepared.

### Continuous Integration and Deployment (CI/CD) with Jenkins

4. Jenkins, our CI/CD tool, pulls code from GitHub immediately after it is committed.
5. Jenkins clones/pulls the code using the Git plugin and executes a Maven build.
6. Maven package is created and Jenkins integrates with SonarQube for code quality validation.
7. Artifacts are uploaded to our artifact repository in Nexus.

### Docker Deployment

8. A Dockerfile is used to build a Docker image from the artifacts.
9. Jenkins installs Docker and creates a Docker image from the artifacts.
10. The Docker image is pushed to Docker Hub.
11. The image is removed from the Jenkins server.

### Kubernetes Deployment

12. The application is deployed as Docker containers in a Kubernetes cluster.
13. Jenkins installs `kubectl` and executes `kubectl apply` to deploy the application in the cluster.
14. Kubernetes pulls the Docker image from Docker Hub and deploys the application in pods.

### Load Balancing and Service Discovery

15. A load balancer service is created inside the cluster to route end-user traffic to the application.
16. The application communicates with the MongoDB database via service discovery.

### Practical Deployment

1. Create an Ubuntu server in AWS with port 8080 open for Jenkins.
2. Install and configure Jenkins on the Ubuntu server.

Please follow the remaining steps outlined in the practical deployment guide to complete the setup and achieve full automation.

For detailed instructions and command references, please refer to the complete documentation provided in the repository.

**Note:** Ensure proper security measures and access controls are implemented throughout the deployment process.
