# End-to-End-Chest-Cancer-Classification-using-MLflow-DVC


## Workflows

1. Update config.yaml
2. Update secrets.yaml (Optional)
3. Update params.yaml
4. Update the entity configuration
5. Update the configuration manager in src/config
6. Update the components
7. Update the pipeline
8. Update main.py
9. Update dvc.yaml


##### cmd

- mlflow ui


### dagshub

[DagsHub](https://dagshub.com/)


Run this to export as environment variables if required.


### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag



## About MLflow & DVC


### MLflow

- Production-grade experiment tracking tool
- Tracks parameters, metrics, and model versions
- Supports logging and tagging of experiments
- Helps in managing the machine learning lifecycle


### DVC

- Lightweight tool for data and model version control
- Useful for proof of concept (POC) projects
- Supports experiment tracking
- Helps in creating reproducible pipelines
- Can be used for pipeline orchestration



# AWS-CICD-Deployment-with-Github-Actions


## 1. Login to AWS Console


## 2. Create IAM user for deployment

Create a user with programmatic access and assign required permissions.

### Required Access

1. EC2 access – used to create and manage virtual machines
2. ECR access – used to store Docker images


### Deployment Overview

1. Build Docker image from source code
2. Push Docker image to ECR repository
3. Launch EC2 instance
4. Pull Docker image from ECR into EC2
5. Run Docker container in EC2


### Required Policies

1. AmazonEC2ContainerRegistryFullAccess
2. AmazonEC2FullAccess



## 3. Create ECR repository to store Docker image

Example repository URI:

566373416292.dkr.ecr.us-east-1.amazonaws.com/chest-cancer-app

Save the URI for later use.



## 4. Create EC2 instance (Ubuntu)



## 5. Open EC2 and install Docker

### optional

sudo apt-get update -y

sudo apt-get upgrade -y


### required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker



## 6. Configure EC2 as self-hosted runner

Go to:

settings > actions > runner > new self-hosted runner

Select operating system and run the commands provided step-by-step in EC2 terminal.



## 7. Setup GitHub Secrets

Add the following secrets in repository settings:

AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION=us-east-1

AWS_ECR_LOGIN_URI=566373416292.dkr.ecr.us-east-1.amazonaws.com

ECR_REPOSITORY_NAME=chest-cancer-app