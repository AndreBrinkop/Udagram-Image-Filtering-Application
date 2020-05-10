# Udagram Image Filtering Application

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into multiple parts:
1. Frontend - Angular web application built with Ionic Framework
2. Backend RESTful API - Node-Express application split into two microservices
3. Reverse Proxy - API Gateway build with Nginx to delegate traffic towards the backend

![Screenshot showing the Udagram Application in action](screenshots/Application.png)

## Getting Started
> _tip_: it's recommended that you start with getting the backend API running since the frontend web application depends on the API.

### Prerequisite
1. The depends on the Node Package Manager (NPM). You will need to download and install Node from [https://nodejs.com/en/download](https://nodejs.org/en/download/). This will allow you to be able to run `npm` commands.
2. Environment variables will need to be set. These environment variables include database connection details that should not be hard-coded into the application code.
#### Environment Script
A file named `set_env.sh` has been prepared as an optional tool to help you configure these variables on your local development environment.
 
We do _not_ want your credentials to be stored in git. After pulling this `starter` project, run the following command to tell git to stop tracking the script in git but keep it stored locally. This way, you can use the script for your convenience and reduce risk of exposing your credentials.
`git rm --cached set_env.sh`

Afterwards, we can prevent the file from being included in your solution by adding the file to our `.gitignore` file.

### Database
Create a PostgreSQL database either locally or on AWS RDS. Set the config values for environment variables prefixed with `POSTGRES_` in `set_env.sh`.

### S3
Create an AWS S3 bucket. Set the config values for environment variables prefixed with `AWS_` in `set_env.sh`.

### Backend Microservices
* To download all the package dependencies, run the command from one of the microservice directories `udagram-restapi-feed/` and `udagram-restapi-user/`:
    ```bash
    npm install .
    ```
* To run the application locally, run:
    ```bash
    npm run dev
    ```
* You can visit `http://localhost:8080/api/v0/feed` (or `http://localhost:8080/api/v0/user`)  in your web browser to verify that the application is running. You should see a JSON payload. Feel free to play around with Postman to test the API's.

### Frontend App
* To download all the package dependencies, run the command from the directory `udagram-frontend/`:
    ```bash
    npm install .
    ```
* Install Ionic Framework's Command Line tools for us to build and run the application:
    ```bash
    npm install -g ionic
    ```
* Prepare your application by compiling them into static files.
    ```bash
    ionic build
    ```
* Run the application locally using files created from the `ionic build` command.
    ```bash
    ionic serve
    ```
* You can visit `http://localhost:80` in your web browser to verify that the application is running. You should see a web interface.

## Run the Application
The application is build up as multiple microservice modules. It is recommended to run the application using the [provided dockcer-compose files](https://github.com/AndreBrinkop/Udagram-Image-Filtering-Application/blob/master/udagram-deployment/docker).

## Deploy the Application to Kubernetes
The application [includes configuration scripts](https://github.com/AndreBrinkop/Udagram-Image-Filtering-Application/tree/master/udagram-deployment/k8s) that make it easy to deploy all components to a Kubernetes cluster using kubectl.
