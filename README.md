# GKE Project Deployment with Kustomize

Welcome to the GKE Project Deployment with Kustomize repository! 🌟 This comprehensive guide is designed to help you navigate through the setup and deployment process using Google Kubernetes Engine (GKE) Autopilot and Google Cloud Shell.

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Getting Started](#getting-started)
   - [Install HELM](#install-helm)
   - [Install nginx-controller](#install-nginx-controller)
4. [Kubernetes Autopilot](#kubernetes-autopilot)
   - [Create a Namespace](#create-a-namespace)
   - [Deploy an Application](#deploy-an-application)
5. [Google Cloud Shell](#google-cloud-shell)
6. [Useful Commands](#useful-commands)

## Introduction
This repository serves as a detailed walkthrough for setting up a Kubernetes environment using GKE Autopilot and managing deployment tasks with Google Cloud Shell.

## Prerequisites
Before diving in, ensure you have the following:
- A Google Cloud Platform (GCP) account with billing enabled.
- Google Cloud SDK (gcloud) installed on your local machine.
- Access to a GKE cluster with Autopilot enabled.

## Getting Started
### Install HELM
To install HELM, run the following commands:

```bash
# Add the HELM repository
helm repo add helm https://helm.sh/helm
# Update the repository
helm repo update
```

# Installation of nginx-controller

To install nginx-controller, execute the following commands:

```bash
# Add the nginx-controller repository
helm repo add nginx https://kubernetes.github.io/ingress-nginx
# Update the nginx-controller repository
helm repo update
```
### Install nginx-controller
```bash
helm install nginx nginx/ingress-nginx 
```
### Search for the nginx-controller chart
```bash
helm search repo nginx
```

# Kubernetes Autopilot

## Create a Namespace

Create a Kubernetes namespace using the following command:

```bash
kubectl create namespace <namespace-name>
```
## Deploy an Application
To deploy an application, apply the YAML configuration file to your namespace:

```bash
kubectl apply -f <path-to-yaml-file>
```
# Google Cloud Shell
Google Cloud Shell offers a browser-based shell for managing GCP resources and Kubernetes clusters.

To access Google Cloud Shell, log in to your GCP Console and click on the "Activate Cloud Shell" button in the upper-right corner.

# Useful commands
Here are some handy commands for Kubernetes environment management:

```bash
# List all ValidatingWebhookConfigurations in all namespaces
kubectl get ValidatingWebhookConfiguration -A
```
## Delete a ValidatingWebhookConfiguration (e.g., nginx-ingress-nginx-admission)
```bash
kubectl delete -A ValidatingWebhookConfiguration nginx-ingress-nginx-admission
```

## List all pods in the current namespace
```bash
kubectl get pods
```
## Create a new Kubernetes namespace (e.g., "dev" or "sit")
```bash
kubectl create ns <namespace-name>
```
## Apply a YAML configuration file to create resources
```bash
kubectl apply -f <path-to-yaml-file>
```

If you have any questions or encounter issues, feel free to open an issue or reach out to the community for assistance.
```bash
Happy learning! 🚀 #gke_project_deployment_with_kustomize
```
