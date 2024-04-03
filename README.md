# React-Todo-list

This is a React To do list app developed by me to learn and enhance my react skills.

 
 ## Tech Stack

  `React` `HTML` `CSS` `Javascript`

 ## Learnings

  - React
  - React hooks
  - React props
  - functions
  - State management
  - data processing
  - Error resolving

  ## Screen-shots
![Screenshot 2023-08-11 215157](https://github.com/MaheshRautrao/React-Todo-list/assets/101188065/04005ab9-b684-493e-8898-afd86bbcaca0)
![Screenshot 2023-08-11 215233](https://github.com/MaheshRautrao/React-Todo-list/assets/101188065/a9414999-bcfc-4857-9243-a2734ab3b229)
![Screenshot 2023-08-11 215243](https://github.com/MaheshRautrao/React-Todo-list/assets/101188065/87f07eb1-ad3c-41bf-969f-3aaee0ea645c)


## Creating a Docker Image for the React Application & Deploying to a Kubernetes Cluster
This guide outlines the process of creating a Docker image for a React application and deploying it to a Kubernetes cluster.

## Pre-requisites
Before proceeding, ensure you have the following pre-requisites:

* An EC2 instance
* Docker installed on your EC2 instance
* Kubernetes installed on your EC2 instance
  
## Steps:
Follow these steps to create a Docker image for your React application and deploy it to a Kubernetes cluster:

## Create a "Dockerfile" for React application
## Build a Docker Image:
Run the following command to build the Docker image:

>> docker build -t <dockerhub-id>/react-app:latest .

## To push the Docker image to Docker Hub:
 >> docker push <dockerhub-id>/react-app:latest

## Create an Amazon EKS Cluster:
Create an EKS cluster using eksctl with the following command:

>> eksctl create cluster --name eks-cluster --region us-east-1 --nodegroup-name standard-workers --node-type t3.medium --nodes 2 --nodes-min 1 --nodes-max 2 --managed

## Check Kubernetes Nodes and Pods:
After the cluster is created, run the following commands to ensure everything is set up correctly:

>> kubectl get nodes  # List the nodes in the Kubernetes cluster
>> kubectl get pods   # List the pods running in the cluster

## Create a Deployment File:
Create a deployment.yaml file to describe your deployment in Kubernetes.
   >> kubectl apply -f deployment.yaml
## Create a Service File:
Create a service.yaml file to expose your deployment as a service in Kubernetes.
   >> kubectl apply -f service.yaml

## Access the Application:
  >> kubectl get svc react-app

Note: The EXTERNAL-IP provided. Open your web browser and navigate to access your deployed React application.

