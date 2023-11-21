# ksl-notifier-k8s
Node app that scrapes KSL Classifieds. Deployed to Google Cloud via k8s.

## Google Cloud Setup Steps
1. Set up Docker repository:
```
gcloud artifacts repositories create ksl-notifier-repo --repository-format=docker --location=us-west3 --description="Docker repository"
```
2. Enable Artifact Registry API:
```
gcloud services enable artifactregistry.googleapis.com
```
3. Configure the Docker command-line tool to authenticate to Artifact Registry:
```
gcloud auth configure-docker us-west3-docker.pkg.dev
```
4. Create a GKE cluster
- Set zone:
```
gcloud config set compute/zone us-west3-b
```
- Now create cluster:
```
gcloud container clusters create ksl-notifier-cluster
```

