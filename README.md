# To-Do Application README

## Project Description

This project is a **simple To-Do application** based on Node.js. The application can be started locally as well as with Docker and Docker Compose.

## Requirements

The following programs are required to use the project:

* Git
* Node.js and npm
* Docker
* Docker Compose

## Clone the Repository

The repository can be cloned with the following command:

**git clone** https://github.com/USERNAME_GITHUB/docker-nodejs-sample.git **docker-nodejs-sample**

## Install Packages

After cloning the repository, the required Node.js packages need to be installed. The command is:

**npm install**

## Start the Application Locally

The application can be started locally with the following command:

**npm start**

Afterwards, the application can be opened in the browser:

http://localhost:3000

## Create Docker Image

Create a Docker image with:

**docker build -t todo-app .**

### Dockerfile Explanation

The Dockerfile defines how the Docker image for the application is created:

```dockerfile
FROM node:20

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "dev"]
```

## Start the Application in Docker

If a `docker-compose.yaml` or `compose.yaml` file is available, the application can be started with the following command:

**docker compose up**

To start the application in the background:

**docker compose up -d**

### The Service for the To-Do Application is Defined in compose.yaml:

```yaml
services:
  todo:
    build:
      context: .
    ports:
      - "3000:3000"
```

## Start the Application with Docker Compose

Start the application with:

* **docker compose up**
* To start it in the background:

  * **docker compose up -d**

## Stop the Application

The application can be stopped with the following command:

**docker compose down**

## Usage
The To-Do application can be used to **create, manage, and organize tasks**. It is suitable for simple everyday task management and can be run locally or in a Docker environment.
