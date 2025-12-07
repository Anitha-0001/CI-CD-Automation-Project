# 🚀 CI/CD Automation Project

This project demonstrates a full Continuous Integration and Continuous Delivery workflow built using industry-standard DevOps tools. The pipeline continuously fetches the application source code, builds it, performs static code analysis, manages artifacts through Nexus, builds Docker images, pushes them to a container registry, and deploys to AWS ECS.

![alt text](<CI_CD through Jenkins.png>)

## 1.🔧Jenkins Setup and CI Foundation

A complete Jenkins environment was prepared from scratch to automate the application build and delivery process.

- Launched an Ubuntu EC2 instance and installed Jenkins and Java JDK
- Completed Jenkins initial setup with recommended plugins
- Installed essential development tools: Git, Maven, JDK, Docker, AWS CLI
- Created the first freestyle job to validate Jenkins and SCM connectivity
- Transitioned to Pipeline as Code (Jenkinsfile) for better automation and version control

## 2.🏗️Continuous Integration Workflow

A full CI pipeline was developed to ensure code quality, repeatability, and automation.

- Pulled source code from Git
- Compiled the application via Maven
- Generated build artifacts (JAR/WAR)
- Executed tests
- Integrated SonarQube for static code analysis
- Implemented Quality Gates to restrict low-quality code
- Published artifacts to Nexus Repository Manager
- Resolved workspace and disk space issues using cleanup strategies

This pipeline covers source retrieval, build, testing, code analysis, and artifact storage.

## 3.🔌Integrations and Plugins

To support advanced CI/CD functionality, multiple plugins and integrations were added in Jenkins:

- Git Plugin
- Maven Integration Plugin
- Pipeline Plugin
- Docker Plugin
- SonarQube Scanner
- Nexus Artifact Uploader
- Slack Notification Plugin

## 4.💬Slack Notifications Integration

Slack was connected to Jenkins to provide real-time build alerts, ensuring immediate visibility for every commit, build, or deployment event.

### Steps Performed

1. Created a Slack app and configured workspace permissions ⚙️
2. Generated a Slack Bot/User token 
3. Installed the **Slack Notification** plugin in Jenkins
4. Added Slack workspace and channel details in Jenkins **Global Configuration** 
5. Updated `Jenkinsfile` to send notifications for:
   - Build start ▶️
   - Build success ✅
   - Build failure ❌


## 5.🐳Docker CI/CD Pipeline

The project included a container-based delivery workflow.

- Installed Docker on the Jenkins EC2 instance
- Built Docker images using Jenkins pipeline stages
- Tagged images using version and build numbers
- Pushed images to Docker Hub or Amazon ECR
- Added deployment steps to trigger AWS ECS updates

## 6.☁️AWS ECS Deployment

A complete deployment workflow was implemented using AWS ECS.

- Created an ECS cluster
- Prepared task definitions for containerized execution
- Configured target groups, load balancers, and port mappings
- Integrated ECS deploy commands into Jenkins pipeline
- Verified deployments through the AWS Console

This enabled fully automated end-to-end CI to CD pipeline execution.

