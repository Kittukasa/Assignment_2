🛠 High-Level Docker & Docker Compose Explanation
---------------------------------------------------
This project uses Docker and Docker Compose to containerize and manage three services: service_1, service_2, and nginx.


🔧 Dockerfiles
-----------------
Each service has its own Dockerfile:

service_1: A Go application that compiles a Go binary and runs it.

service_2: A Python Flask app that installs dependencies and runs the server on port 8002.

nginx: Uses a custom NGINX configuration to reverse proxy requests to service_1 and service_2.

All Dockerfiles are minimal, using official base images and optimized for small size and fast builds.


📦 Docker Compose
---------------------
The docker-compose.yml file:

Builds and starts all three containers.

Connects them using a custom bridge network (appnetwork) so they can communicate by name.

Sets up health checks on service_1 and service_2 using their /ping endpoints.

Configures NGINX to only start once both services are healthy.

Maps NGINX to port 8080 on the host for external access.


🔁 Reverse Proxy with NGINX
-----------------------------
NGINX is configured to:

Route /service1/ traffic to service_1

Route /service2/ traffic to service_2

Show a simple message at / to confirm NGINX is running

This setup simulates a typical microservice architecture with internal services behind a reverse proxy.



![alt text](<Screenshot 2025-06-25 213209.png>) 

![alt text](<Screenshot 2025-06-25 213445.png>) 

![alt text](<Screenshot 2025-06-25 213625.png>)

![alt text](<Screenshot 2025-06-25 213701.png>)

![alt text](<Screenshot 2025-06-25 213715.png>)
