# DockerLap with WeatherForecast api

## Overview

This project demonstrates how to use Docker with a .NET Core 7 application. It includes instructions for building and running the project using MSBuild and Docker commands, as well as using Docker Compose for managing multi-container applications.

### Relate images with
- MySql for database.
- PHP MyAddmin for database tools.

## Project Setup

### .NET Core 7

This project is created with .NET Core 7. Ensure that you have the .NET Core SDK installed on your machine to build and run the application.

## Commands

### MSBuild Command

To build the project using MSBuild, use the following command:

```bash
dotnet msbuild
```

This command will compile your .NET Core 7 application and generate the necessary output files.

### Docker Build Command
To build the Docker image for this project, use the Dockerfile included in the repository. Run the following command in the directory containing the Dockerfile:
```bash
docker build -t my-dotnetcore-app .
```
Replace my-dotnetcore-app with your preferred image name. This command will create a Docker image based on the Dockerfile.

### Docker Run Command
To run a container from the Docker image you built, use the following command:
```bash
docker run -d -p 8080:80 my-dotnetcore-app
```
This command runs the container in detached mode and maps port 80 in the container to port 8080 on your host machine. Adjust the port numbers as needed.

### Docker Compose Command
If you are using Docker Compose to manage your services, use the following command to build and run your containers:
```bash
docker-compose up --build
```
This command will build and start the services defined in your docker-compose.yml file.
