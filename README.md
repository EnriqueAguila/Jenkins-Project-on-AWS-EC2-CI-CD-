# Jenkins-Project-on-AWS-EC2-CI-CD-
Deploying Jenkins within the AWS environment using an EC2 instance.

# Introduccion Jenkis
Jenkins is an open-source automation tool used for continuous integration (CI) and continuous delivery (CD). It automates software development tasks such as building, testing, and deploying applications, improving software efficiency and quality.

# CI/CD Deployment with Jenkins on AWS EC2

**Jenkins on EC2** In this project, we will implement a Continuous Integration (CI) and Continuous Delivery (CD) pipeline using Jenkins on an AWS EC2 instance. The goal is to automate the process of building, testing, and deploying an application.

## Objetivos
-Jenkins: CI/CD automation server
-GitHub: Code repository
-AWS EC2: Virtual instance for Jenkins
## CI/CD pipeline:
-Build: Jenkins retrieves the code from GitHub and builds the application.
-Testing: Jenkins runs unit and integration tests to validate the application.
-Deployment: Jenkins deploys the application to the test server.
-Validation: Jenkins runs validation tests to ensure the application is working properly.
-Production deployment: Jenkins deploys the application to the production server.


## Commands to run in programmatic access in the EC2 CLI.
![1 instalacion jenkins](https://github.com/user-attachments/assets/4c458705-b496-4d0e-bdf0-b17d3a83efc8)

```bash
az search service create --name my-search-service --resource-group my-resource-group --sku Standard
az search index create --name my-index --service-name my-search-service --fields "title, content"

![2 instalacion](https://github.com/user-attachments/assets/d6171a94-a305-487d-9975-4581fe53f0ba)

## Complete installation
![3 instalacion](https://github.com/user-attachments/assets/f4b68ffb-5e0d-4ca4-b1a9-5b73e7d3852b)

```sh
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
# Add required dependencies for the jenkins package
sudo yum install fontconfig java-21-openjdk
sudo yum install jenkins
sudo systemctl daemon-reload
```

### 1. Install Amazon Corretto
Running this command will install Amazon Corretto 21 on your system, allowing you to develop and run Java applications.
![4 instalacion completa](https://github.com/user-attachments/assets/cedf0c49-7cec-41e3-b32d-d4f5a5110210)

```sh
sudo dnf install java-21-amazon.corretto-devel -y
```
java --versión

## Run and view the status of Jenkins on EC2.
![5 jenkins status](https://github.com/user-attachments/assets/1ef13939-a6fe-4876-bb55-410b228bd0f7)

```sh
sudo systemctl enable Jenkins
sudo systemctl start Jenkins
sudo systemctl status Jenkins
```

### 2. Copy the IP of the instance port 8080
Example to paste into a browser tab: http://123.24.45.98:8080
![6 jenkins unlok](https://github.com/user-attachments/assets/dc1d810c-acb0-4321-a546-95c0372df1c2)


### 3. Security group
Add the security group on port 8080 and in source myIP and put the instance's with the slash /32
![7 agregar la regla ip](https://github.com/user-attachments/assets/7338d398-f5b6-4f4e-a985-6d5b2e9099d6)


### Jenkins
![jenkins ya en funcion1](https://github.com/user-attachments/assets/8818d666-f0c0-46b5-b92f-b45b9bbaf97d)

In Jenkins, branch management in a Git repository is essential for implementing Continuous Integration (CI) and Continuous Delivery/Deployment (CD) workflows. Here's how Jenkins handles branches:
1. Configuring Branches in Jenkins
You can configure Jenkins to automatically build when changes are detected on a specific branch of a Git repository. This is typically done in the Jenkins job configuration, specifying the branch or branches you want to monitor.
2. Multibranch Pipeline
Jenkins offers the "Multibranch Pipeline" feature, which allows you to create jobs that automatically detect and build branches in a Git repository according to a specified pattern.


### Jenkins Pipeline
![jenkins pipeline3](https://github.com/user-attachments/assets/93584ac4-eedb-4c35-990e-2049afa8d7c2)

A Jenkins Pipeline is a suite of plugins that supports the deployment and integration of continuous delivery pipelines in Jenkins. A Jenkins pipeline is a sequence of automated tasks that execute in a series of defined stages, enabling the efficient and repeatable building, testing, and delivery of applications.
Key components of a Jenkins Pipeline:

Stages: A pipeline is divided into stages, such as "Build," "Test," and "Deploy." Each stage contains a series of steps that execute in order.
Steps: Steps are the basic units of work within a stage. They can include shell commands, script execution, API calls, etc.
Agents: Agents are the nodes where pipelines run. They can be the Jenkins master or slave nodes configured to perform specific jobs.
