# Step 1: Create a file "DockerFile" under project root folder

# Step 2: Open terminal on the project directory and build Accounts maven project
	mvn clean
	mvn install -X

# Step 3: Need to build docker image
	docker build . -t ibrahimcseku/accounts:s4
Here, docker build . -t {dockerHubId}/{imageName}:{version}

# Step 4: Command to see all docker images:
	docker images
	
# Step 5: Create and run docker container
	docker run -d -p 8080:8080 ibrahimcseku/accounts:s4
	
# Step 6: Use below command to see all container present status
	docker ps -a
	
# Step 7: Can Start and Stop container using container ID
	docker ps -a
	docker start {ContainderId}
	docker stop {ContainerId}	
	
# To push an docker image or a repository to a remote registry (for my case I am pushing to docker hub remote repository)
	docker image push docker.io/ibrahimcseku/accounts:s4
	
# To pull an image or a repository from a registry		
	docker image pull docker.io/ibrahimcseku/accounts:s4	
	
# To run all the container by a single command create docker-compose.yml file and use following command to up/down docker container.
	docker compose up -d
	docker compose down
	
# To start/stop existing docker compose container use following command:
	docker compose start
	docker compose stop 	