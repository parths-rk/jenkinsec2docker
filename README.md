# Jenkins CI Pipeline with Docker

## Goal
Build a basic Jenkins pipeline that triggers builds manually and creates Docker images, demonstrating CI fundamentals.

## Stack
- Jenkins
- Docker
- GitHub
- Linux

## What I Implemented
- Jenkins installation on Linux
- Jenkins dashboard access
- Job creation and configuration
- Manual pipeline triggers
- Docker image build from Jenkins
- Build verification using console output
- Docker image validation locally

## Workflow
1. Jenkins job configured
2. Pipeline triggered manually
3. Docker image built
4. Console logs reviewed for success

## Current Scope
- Manual Jenkins pipeline
- Docker build automation

Webhook-based auto-triggering and full CI/CD deployment are not implemented in this phase.

## Pipeline Architecture
Developer
   │
   │ Push Code
   ▼
GitHub Repository
   │
   │ Webhook Trigger
   ▼
Jenkins CI Server
   │
   ├── Pull Source Code
   ├── Build Docker Image
   ├── Tag Image
   ├── Push Image to Docker Hub
   │
   ▼
Docker Image Repository


## Repository Structure
jenkins-docker-ci-pipeline
│
├── app
│   └── application code
│
├── Dockerfile
│
├── Jenkinsfile
│
└── README.md

## Verification
- Jenkins jobs execute successfully
- Docker images created
- Console output confirms pipeline stages

## Screenshots
Available in screenshots folder.
