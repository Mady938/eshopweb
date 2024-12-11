# Project Setup with Docker

## Prerequisites
- Docker
- Docker Compose

## Getting Started

### 1. Clone the Repository
```sh
git clone <repository-url>
cd <repository-directory>
```

### 2. Create and Edit the `.docker.env` File
Create a `.docker.env` file in the root directory of the project and add the necessary environment variables. Here is an example:

```sh
DB_ROOT_PASSWORD=rootpassword
DB_DATABASE=richzone
DB_USERNAME=richzone
DB_PASSWORD=password
HOST_MACHINE_PMA_PORT=8001
HOST_MACHINE_MYSQL_PORT=3306
HOST_MACHINE_UNSECURE_HOST_PORT=80
HOST_MACHINE_SECURE_HOST_PORT=443
XDEBUG_PORT=9003
PMA_UPLOAD_LIMIT=100M
PMA_MEMORY_LIMIT=100M
```

### 3. Install PHP Dependencies
Before starting the Docker containers, you need to install PHP dependencies using Composer. Run the following command:

```sh
composer install
```

### 4. Build and Start the Docker Containers
Build and start the Docker containers using Docker Compose:

```sh
docker-compose up --build
```

This command will build the Docker images and start the containers as defined in the `docker-compose.yml` file.

### 5. Access the Application
- **Web Application**: Open your browser and navigate to `http://localhost` (or the port specified in your `.docker.env` file).
- **phpMyAdmin**: Open your browser and navigate to `http://localhost:8001` (or the port specified in your `.docker.env` file).

### 6. Running Node.js Commands
To run Node.js commands such as `npm run build`, you can use the Node.js service defined in the `docker-compose.yml` file. For example:

```sh
docker-compose run node npm run build
```

## Notes
- Ensure that the `.docker.env` file is correctly formatted and contains all the necessary environment variables.
- The `docker-compose.yml` file is configured to use a multi-stage build for the `webserver` service, which includes building the Node.js application.
- The `firebase-config.js` file is included in the `.gitignore` file, so make sure to configure it properly before running the application.

## Troubleshooting
- If you encounter any issues with file permissions, ensure that the `.docker.env` file and other project files have the correct permissions.
- Check the Docker and Docker Compose documentation for any additional troubleshooting steps.

This README provides the necessary steps to set up and run the project using Docker. Make sure to follow each step carefully to ensure a smooth setup process.