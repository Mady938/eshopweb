# Project Setup with Docker

## Prerequisites
- Docker

## Getting Started

### 1. Clone the Repository
```shell
git clone <repository-url>
cd <repository-directory>
```

### 2. Create and Edit the `.docker.env` File
Edit `.env` file in the root directory of the project and add the necessary environment variables. Here is an example:

```shell
DB_DATABASE=richzone
DB_USERNAME=richzone
DB_PASSWORD=password
```

### 3. Install PHP and NPM Dependencies
Before starting the Docker containers, you need to install PHP and NPM dependencies. Run the following commands:

```shell
docker exec <container-name> composer install
docker exec <container-name> npm install
```

### 4. Build and Start the Docker Containers
Build and start the Docker containers using Docker Compose:

```shell
docker compose up -d
```

This command will build the Docker images and start the containers as defined in the `docker-compose.yml` file.

### 5. Access the Application
- **Web Application**: Open your browser and navigate to `http://localhost` (or the port specified in your `.env` file).
- **phpMyAdmin**: Open your browser and navigate to `http://localhost:8080` (or the port specified in your `.env` file).

### 6. Running Node.js Commands
To run Node.js commands such as `npm run build`, you can use the Node.js package included with the container. For example:

```shell
docker exec <container-name> npm run build
```

### 7. Shutting down the Docker Containers
Stopping the Docker Containers using Docker Compose:

```shell
docker compose down
```

## Notes
- Ensure that the `.env` file is correctly formatted and contains all the necessary environment variables.
- The `docker-compose.yml` file is configured to use a multi-stage build for the `webserver` service, which includes building the Node.js application.
- The `firebase-config.js` file is included in the `.gitignore` file, so make sure to configure it properly before running the application.

## Troubleshooting
- If you encounter any issues with file permissions, ensure that the `.env` file and other project files have the correct permissions.
- Check the Docker and Docker Compose documentation for any additional troubleshooting steps.

This README provides the necessary steps to set up and run the project using Docker. Make sure to follow each step carefully to ensure a smooth setup process.