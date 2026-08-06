# GitOps deployment repository for Site PDF Converter

This repository is the deployment layer for my Site PDF Converter project. It contains the Kubernetes and Helm manifests used to run the application in a real environment and is designed to support a clean GitOps-based demo.

## Purpose of this repository

This repo is used to show how application deployment can be managed declaratively through Git. Instead of manually applying resources, the desired state of the application is stored here and synced to the cluster by Argo CD.

## What is included

The repository contains deployment manifests for the main parts of the application:

- API service
- UI service
- Ingress routing
- Serverless Lambda function definition

These resources are organized under the chart structure for the application.

## Repository structure

- demoapp/demoapp/charts/api - backend API deployment resources
- demoapp/demoapp/charts/ui - frontend UI deployment resources
- demoapp/demoapp/charts/ingress - public access routing through ingress
- demoapp/demoapp/charts/lambda - Lambda deployment definition for the conversion workflow

## How this fits into the demo

1. The application source and CI pipeline are handled separately.
2. This repository stores the deployment state for the application.
3. Argo CD watches the repository and applies the desired state to the cluster.
4. The result is a visible, repeatable deployment that can be demonstrated live.

## Demo use case

This repository is useful for demonstrating:

- GitOps deployment flow
- Kubernetes-based application delivery
- Argo CD sync and reconciliation
- Helm-managed application resources
- Integration of a web app with a serverless conversion process

## Main components deployed

- API workload: Kubernetes Deployment and Service
- UI workload: Kubernetes Deployment and Service
- Ingress: routes traffic to the application
- Lambda: AWS Lambda function managed through Kubernetes resources

## Typical workflow

- Update the deployment manifests or image references
- Commit and push the changes
- Let Argo CD detect and sync the new state
- Verify that the application is working as expected

## Notes

This repository should be treated as the operational deployment layer for the Site PDF Converter project. It is meant to support a presentation, demo, or portfolio-style walkthrough of a complete GitOps deployment setup.
