
# Docker Architecture

Docker uses a client-server architecture. The docker client talks to the Docker daemon, which used to building, running, and distributing the Docker containers. The Docker client and daemon communicate using a REST API, over UNIX sockets, or a network interface.

![Docker Architecture](./Assets/Docker_architectue.png)

## There are five major components in the Docker architecture:

a) **Docker Daemon** listens to Docker API requests and manages Docker objects such as images, containers, networks and volumes.

b) **Docker Clients**: With the help of Docker Clients, users can interact with Docker. Docker client provides a command-line interface (CLI) that allows users to run, and stop application commands to a Docker daemon.

c) **Docker Host** provides a complete environment to execute and run applications. It comprises of the Docker daemon, Images, Containers, Networks, and Storage.

d) **Docker Registry** stores Docker images. Docker Hub is a public registry that anyone can use, and Docker is configured to use images on Docker Hub by default. You can run your own registry on it.

e) **Docker Images** are read-only templates that you build from a set of instructions written in Dockerfile. Images define both what you want your packaged application and its dependencies to look like what processes to run when it’s launched.

Resouces: The best article i prefer to everyone to go through if you want to learn deeply with theoreotical knowledge and understanding.
- https://k21academy.com/docker-kubernetes/docker-tutorial/

--- 



# Getting Started

Before diving into best practices, ensure you have Docker installed on your machine. You can follow Docker installation guide from this repository [here](./Docker.md)

## Best Practices for Writing Dockerfiles

Writing efficient, secure, and maintainable Dockerfiles is crucial for any DevOps engineer. Here are some best practices to follow:

### 1. Use Official Base Images

Using official base images ensures you are starting from a reliable and well-maintained foundation.

**Example:**
```Dockerfile
# Bad Practice
FROM ubuntu:latest

# Good Practice
FROM python:3.9-slim
```

### 2. Minimize the Number of Layers

Each command in a Dockerfile creates a new layer. To keep the image size small, combine commands where possible.

**Example:**
```Dockerfile
# Bad Practice
RUN apt-get update
RUN apt-get install -y python3

# Good Practice
RUN apt-get update && apt-get install -y python3
```

### 3. Use .dockerignore

A `.dockerignore` file works similarly to a `.gitignore` file and helps to exclude unnecessary files from the Docker build context.

**Example:**
```plaintext
# .dockerignore
node_modules
*.log
```

### 4. Leverage Caching

Docker caches layers to speed up the build process. Arrange commands to maximize the use of caching.

**Example:**
```Dockerfile
# If requirements.txt doesn't change, the following layer will be cached
COPY requirements.txt /app/
RUN pip install -r /app/requirements.txt

# This layer will be rebuilt only if the source code changes
COPY . /app/
```

### 5. Use Multi-Stage Builds

Multi-stage builds help to create smaller and more secure final images by separating the build environment from the runtime environment.

**Example:**
```Dockerfile
# First stage: build
FROM node:14 AS build
WORKDIR /app
COPY . .
RUN npm install && npm run build

# Second stage: runtime
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
```

### 6. Avoid Hardcoding Secrets

Use Docker secrets or environment variables to manage sensitive information.

**Example:**
```Dockerfile
# Bad Practice
ENV API_KEY=your_api_key

# Good Practice
# Use docker-compose secrets or pass at runtime
# docker run -e API_KEY=your_api_key your_image
```

### 7. Optimize for Security

Run your application as a non-root user and keep the image up-to-date with security patches.

**Example:**
```Dockerfile
# Add a user and switch to it
RUN useradd -m myuser
USER myuser
```

### 8. Keep Dockerfile Clean and Readable

Use comments to explain complex commands and keep the Dockerfile tidy.

**Example:**
```Dockerfile
# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 && \
    rm -rf /var/lib/apt/lists/*

# Copy source code
COPY . /app
```

### 9. Specify Exact Versions

Pin versions of dependencies to ensure consistency across builds.

**Example:**
```Dockerfile
# Bad Practice
RUN pip install flask

# Good Practice
RUN pip install flask==1.1.2
```

### 10. Document Your Dockerfile

Provide documentation within the Dockerfile to explain the purpose of each step.

**Example:**
```Dockerfile
# Use official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Run app.py when the container launches
CMD ["python", "app.py"]
```

## Conclusion

By following these best practices, you can write Dockerfiles that are efficient, secure, and easy to maintain. Happy Dockerizing!


---