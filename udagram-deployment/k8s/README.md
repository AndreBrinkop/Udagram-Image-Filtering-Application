# Udagram Image Filtering Microservice

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

### Deploy to Kubernetes
You'll need to install kubectl. Open a new terminal within the project directory and run:

1. Deploy the containers: `kubectl apply -f deployments/.`
2. Deploy the services: `kubectl apply -f services/.`
