# Step 1: Set Up Your Workspace

## touch quote_{disp,gen}/Dockerfile

## FROM: Gets a Python distribution from Docker images

## WORKDIR: Changes the working directory

## COPY: Copies the content of the working directory into a new directory


# Step 2: Build the Docker Images 

## docker build -t quote-gen-service ./quote_gen
## docker build -t quote-disp-service ./quote_disp


# Run the Docker Containers

## docker run -d --name quote-gen-container -p 5000:5000 quote-gen-service

## docker run -d --name quote-disp-container -p 5001:5001 quote-disp-service

### for stoping

## docker stop $(docker ps -a -q)
## docker rm $(docker ps -a -q)

#  Create a Docker Network

## docker network create quote-network

## docker run -d --name quote-gen-container --network quote-network -p 5000:5000 quote-gen-service

## docker run -d --name quote-disp-container --network quote-network -p 5001:5001 quote-disp-service


## docker network inspect quote-network

# Create a Docker Compose Manifest

### docker-compose.yaml

## docker-compose up -d


# {
##  docker stop $(docker ps -a -q)
##  docker rm $(docker ps -a -q) 
##  docker-compose stop
# }


