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


