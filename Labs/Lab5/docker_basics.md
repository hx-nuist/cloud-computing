# Docker Basic Knowledge Notes

## 1. Difference Between Containers and Images

### Container
- A container is a running instance of an image
- Contains the application and all its dependencies
- Is a lightweight isolated environment
- Can be created, started, stopped, deleted, and paused
- Each container has its own network, storage, and process space

### Image
- An image contains all the filesystems, code, and dependencies needed to run an application
- Is a read-only template
- Can be used to create multiple containers
- Defined and built through Dockerfile
- Supports layered storage for easy sharing and reuse

## 2. Role of Docker Compose

- **Service Orchestration**: Define and run multi-container Docker applications
- **Configuration Management**: Centralize configuration management for all services
- **Dependency Management**: Define dependencies between services
- **Network Management**: Automatically create and configure networks
- **Volume Management**: Manage creation and mounting of data volumes
- **One-click Deployment**: Start the entire application with a single command

## 3. Container Network Modes

### 1. Bridge Mode
- Default network mode
- Each container has an independent IP address
- Containers can communicate via IP addresses
- Host accesses containers through port mapping

### 2. Host Mode
- Containers directly use the host network
- Containers share the host's network namespace
- Best performance but lower security

### 3. None Mode
- Containers have no network interfaces
- Only used in scenarios requiring complete network isolation

### 4. Container Mode
- Multiple containers share the same network namespace
- Often used for containers that need close collaboration

## 4. Data Persistence Solutions

### 1. Volumes
- Storage area managed by Docker
- Located in the Docker host's filesystem
- Suitable for persisting important data like database information
- Supports sharing across containers

### 2. Bind Mounts
- Mount directories or files from the host filesystem to containers
- Can mount any directory
- Suitable for development environments, facilitating file synchronization

### 3. tmpfs
- Data stored in memory
- Data lost when container stops
- Suitable for temporary data storage

## 5. Basic Structure of Dockerfile

```dockerfile
# Base image
FROM ubuntu:20.04

# Maintainer information
LABEL maintainer="yourname@example.com"

# Install dependencies
RUN apt-get update && apt-get install -y nginx

# Copy files
COPY index.html /var/www/html/

# Expose port
EXPOSE 80

# Start command
CMD ["nginx", "-g", "daemon off;"]
```

## 6. Common Docker Commands

### Container Management
```bash
# Run container
docker run [options] image [command]

# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Start/stop/restart container
docker start/stop/restart container_name

# Delete container
docker rm container_name

# Enter container
docker exec -it container_name /bin/bash
```

### Image Management
```bash
# List local images
docker images

# Pull image
docker pull image_name

# Delete image
docker rmi image_name

# Build image
docker build -t image_name .

# Push image to registry
docker push image_name
```

### Network Management
```bash
# List networks
docker network ls

# Create network
docker network create network_name

# Connect container to network
docker network connect network_name container_name
```

### Volume Management
```bash
# List volumes
docker volume ls

# Create volume
docker volume create volume_name

# View volume details
docker volume inspect volume_name

# Delete volume
docker volume rm volume_name
```

## 7. Best Practices

1. **Use Official Images**: Pull officially certified images from Docker Hub
2. **Minimize Image Size**: Use lightweight base images like Alpine
3. **Layered Building**: Organize Dockerfile properly to utilize caching
4. **Single Responsibility Principle**: Each container runs only one process
5. **Use Environment Variables**: Avoid hardcoding configurations
6. **Data Persistence**: Use volumes to manage important data
7. **Container Security**: Regularly update images, restrict container permissions
8. **Log Management**: Configure appropriate log drivers
9. **Monitor Containers**: Use Docker stats or third-party tools to monitor container performance
10. **Automated Deployment**: Implement automated build and deployment with CI/CD tools

## 8. Common Issues and Solutions

### Issue 1: Port Conflict
**Solution**: Use different host port mappings or stop other services occupying the port

### Issue 2: Container Cannot Access External Network
**Solution**: Check Docker network configuration, ensure containers use the correct network mode

### Issue 3: Data Loss
**Solution**: Use volumes or bind mounts to persist data

### Issue 4: Image Build Failure
**Solution**: Check Dockerfile syntax, ensure dependency installation commands are correct

### Issue 5: Container Exits Immediately After Startup
**Solution**: Check container logs, ensure startup command is correct, avoid background running commands causing container exit