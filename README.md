# VOIS_CICD_EKS_Task

This repository contains the Terraform code and configurations for deploying a CI/CD pipeline on AWS EKS (Elastic Kubernetes Service) as part of the VOIS task.

The CI/CD pipeline is designed to automate the deployment of applications using Kubernetes. It utilizes infrastructure as code principles to provision the necessary AWS resources and Kubernetes infrastructure, and then configures a CI/CD workflow using Jenkins.

This repository is created as part of the VOIS task and serves as a demonstration of deploying a completely private EKS cluster. All cluster configurations are managed with Ansible, including the deployment and configuration of a bastion host for secure communication.

Jenkins is deployed using Ansible and runs as a Pod within the EKS cluster. It is utilized to create a pipeline and facilitate the deployment of applications. The pipeline is configured to build, test, and deploy the application using Kubernetes manifests. The deployed application is then exposed through a load balancer for external access.

This repository provides a comprehensive example of deploying a private EKS cluster, securing communication with a bastion host, and setting up a CI/CD pipeline using Jenkins.

![nabil_digram](https://github.com/AhmedNabilSharawy/VOIS_CICD_EKS_Task_Full/assets/83243320/7c18f149-900a-482a-8a74-71d83e1ba831)
