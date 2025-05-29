
# Docker Interview Questions - Beginner to Advanced

### 1. What is Docker?
 A platform for developing, shipping and running containerized applications
 Enables consistent environments across different stages of development
 Containers package application code and dependencies together


### 2. What is containerization?
 Process of packaging application and dependencies into a standardized unit
 Ensures application runs consistently across different environments

### 3. What is the difference between Docker and Virtual Machines?
 Docker shares host OS kernel, VMs have complete OS copy
 Docker starts in seconds, VMs take minutes
 Docker is lightweight, VMs are heavyweight
 Docker uses less resources, VMs require more resources

### 4. What are Docker containers?
 Runnable instances of Docker images
 Isolated environments with their own processes, networks and mounts
 Can be started, stopped, moved and deleted
    OR
 A standalone, executable package that includes everything needed to run an application
 Contains code, runtime, libraries, environment variables, config files
 Isolated from other containers and host system


### 5. What is a Docker image?
 Read-only template used to create containers
 Contains application code, runtime, libraries and dependencies
 Built using instructions from a Dockerfile

### 6. What is a Dockerfile?
 Text file containing instructions to build a Docker image
 Defines the environment and commands to run the application
 Uses specific syntax and commands like FROM, RUN, COPY etc.

 Example:
```
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]

```

### 7. What is Docker Hub?
 Cloud-based registry service for Docker images
 Allows sharing and managing Docker images
 Contains official and community images

### 8.1. Basic Docker commands:
docker pull <image>      Download image from registry
docker push <image>      Upload image to registry
docker run <image>       Create and start container
docker ps               List running containers
docker images           List available images

### 8.2. Key Docker commands:
 Build image:
docker build -t myapp .

 Run container:
docker run -d -p 3000:3000 myapp

 List containers:
docker ps

 Stop container:
docker stop <container_id>

 Remove container:
docker rm <container_id>


### 9. What is the difference between CMD and ENTRYPOINT in Dockerfile?
 CMD provides default commands that can be overridden
 ENTRYPOINT specifies the command that will always be executed

### 10. What is Docker cache?
 Layer caching mechanism used during image builds
 Speeds up build process by reusing unchanged layers
 Can be disabled using --no-cache flag

### 11. What is Docker Compose?
 Tool for defining/running multi-container applications
 Uses YAML file to configure application services
 Manages application lifecycle (start, stop, rebuild)
 Example `docker-compose.yml`:
```
version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
  db:
    image: mongo
    ports:
      - "27017:27017"
```

### 12. What is Docker Swarm?
 Native clustering and orchestration solution for Docker
 Turns host pool into single virtual host
 Provides high availability and load balancing

### 13. Explain Docker networking types:
 bridge - Default isolated network
 host - Uses host network stack
 none - Disables networking
 overlay - Multi-host networking
 macvlan - Assigns MAC address to container
 Example:
`docker run --network=host myapp`

### 14. What are Docker volumes?
 Mechanism for persisting and sharing data
 Independent of container lifecycle
 Can be shared between containers
 Example:
`docker run -v /host/path:/container/path myapp`

### 15. What is multi-stage build?
 Build process using multiple temporary stages
 Reduces final image size
 Separates build-time dependencies from runtime

### 16. Explain Docker architecture:
 Client-server architecture
 Docker daemon (dockerd)
 Docker client (docker)
 Docker registry
 Docker objects (images, containers)

### 17. What is container orchestration?
 Management of multiple containers
 Handles scheduling, scaling, networking
 Examples: Kubernetes, Docker Swarm

### 18. What are Docker networks?
 Provide isolation between containers
 Enable container communication
 Support different network drivers

### 19. What is Docker registry?
 Storage and distribution system for Docker images
 Can be public (Docker Hub) or private
 Supports image versioning

### 20. What is Docker security scanning?
 Vulnerability scanning for Docker images
 Identifies known security issues
 Available in Docker Hub and Enterprise


### 21. Explain Docker storage drivers:
 overlay2 - Default on modern Linux
 devicemapper - Block-level storage
 aufs - Union filesystem
 btrfs - Copy-on-write filesystem
 zfs - Advanced filesystem features

### 22. What is Docker content trust?
 Digital signing mechanism for Docker images
 Ensures image authenticity
 Uses The Update Framework (TUF)

### 23. Explain Docker namespaces:
 pid - Process isolation
 net - Network isolation
 mnt - Mount isolation
 user - User isolation
 uts - Hostname isolation
 ipc - IPC isolation

### 24. What are Docker control groups (cgroups)?
 Resource limitation and accounting
 CPU, memory, disk I/O controls
 Ensures fair resource sharing

### 25. Explain Docker overlay network:
 Multi-host networking
 Uses VXLAN encapsulation
 Enables container communication across hosts

### 26. What is Docker BuildKit?
 Next-generation build engine
 Concurrent dependency resolution
 Enhanced build cache
 Better performance

### 27. Explain Docker health checks:
 Container health monitoring
 Custom health check commands
 Automatic container management

### 28. What is Docker rootless mode?
 Runs Docker daemon without root privileges
 Enhanced security
 Limited functionality

### 29. Explain Docker secrets:
 Secure storage for sensitive data
 Encrypted at rest and in transit
 Available only to authorized containers

### 30. What is Docker checkpoint/restore?
 Container state preservation
 Live migration support
 Experimental feature

### 31. Advanced security practices:
 Run as non-root user
 Use security options
 Implement content trust
 Regular security updates
 Resource limitations

### 32. Performance optimization:
 Layer optimization
 Cache utilization
 Multi-stage builds
 Resource constraints
 Network optimization

### 33. Debugging techniques:
 docker logs
 docker exec
 docker inspect
 docker stats
 docker events

### 34. Container monitoring:
 Resource usage tracking
 Performance metrics
 Log aggregation
 Alert configuration

### 35. High availability setup:
 Replication
 Load balancing
 Health monitoring
 Failover configuration

### 36. CI/CD integration:
 Automated builds
 Testing in containers
 Image promotion
 Deployment strategies

### 37. Docker API usage:
 RESTful API endpoints
 SDK integration
 Custom automation
 Remote management

### 38. Storage management:
 Volume plugins
 Backup strategies
 Data persistence
 Cleanup policies

### 39. Network troubleshooting:
 DNS issues
 Network isolation
 Port conflicts
 Connectivity problems

### 40. Resource management:
 Memory limits
 CPU constraints
 Storage quotas
 Network bandwidth

### 41. Image optimization:
 Size reduction
 Layer management
 Base image selection
 Dependency cleanup

### 42. Service discovery:
 Container registration
 Service lookup
 Load balancing
 Health checking

### 43. Logging strategies:
 Log drivers
 Log rotation
 Centralized logging
 Log analysis

### 44. Backup strategies:
 Volume backup
 Image backup
 Configuration backup
 Disaster recovery

### 45. Security hardening:
 AppArmor profiles
 SELinux policies
 Capability restrictions
 Network policies

### 46. Performance monitoring:
 Resource metrics
 Container stats
 Network monitoring
 Storage performance

### 47. Scaling strategies:
 Horizontal scaling
 Vertical scaling
 Auto-scaling
 Load distribution

### 48. Disaster recovery:
 Backup verification
 Recovery procedures
 Data consistency
 Service restoration

### 49. Compliance requirements:
 Audit logging
 Access controls
 Policy enforcement
 Regulatory compliance

### 50. Advanced networking:
 Custom networks
 Network plugins
 Traffic control
 Service mesh integration

### 51. Docker best practices:
 Use .dockerignore file
 Minimize number of layers
 Use multi-stage builds
 Keep images small
 Don't run as root
 Use specific tags instead of latest

### 52. Debugging containers:
 View logs:
docker logs <container_id>
