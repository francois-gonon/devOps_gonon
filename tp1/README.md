1-1 For which reason is it better to run the container with a flag -e to give the environment variables rather than put them directly in the Dockerfile?
It allows for more security as env variables are hidden and compartimentalized soit doesnt impede on variables that could be used for other services

1-2 Why do we need a volume to be attached to our postgres container?
We need a volume to make the data perisistant and independant from container delete/restart

1-3 Document your database container essentials: commands and Dockerfile.
running : 
- docker run -d --name my-database --network app-network -e POSTGRES_DB=db -e POSTGRES_USER=usr -e POSTGRES_PASSWORD=pwd -v pgdata:/var/lib/postgresql/data my-database:1.0
- docker run -p "8090:8080" --network app-network --name=adminer -d adminer


1-4 Why do we need a multistage build? And explain each step of this dockerfile.
Multistage keeps final image small, separates build/runtime, and avoids shipping build tools

1-5 Why do we need a reverse proxy?
a reverse proxy allows for only 1 entry point for all containers and enables load balancing between services

1-6 Why is docker-compose so important?
docker-compose lets you run a series of containers without having to start them manually and allows you to have a custom configuration 

1-7 Document docker-compose most important commands.
docker-compose up -d: start services in detached mode
docker-compose down: stop and services
docker-compose ps: list running services
docker-compose logs: view logs
docker-compose build: rebuild images

1-8 Document your docker-compose file.
my dokcer files containes : config otpions for the 3 containers, network and volume configuration

1-9 Document your publication commands and published images in dockerhub.
# Tag 
docker tag my-database:1.0       francoisgonon/my-database:1.0
docker tag simple-api:1.0        francoisgonon/simple-api:1.0
docker tag my-httpd:1.0          francoisgonon/my-httpd:1.0

# Push
docker push francoisgonon/my-database:1.0
docker push francoisgonon/simple-api:1.0
docker push francoisgonon/my-httpd:1.0

# Online
https://hub.docker.com/r/francoisgonon/my-database
https://hub.docker.com/r/francoisgonon/simple-api
https://hub.docker.com/r/francoisgonon/my-database

1-10 Why do we put our images into an online repo?
Online repos enables sharing, versioning, CI/CD integration, and reproducible deployments across other machines/environments
