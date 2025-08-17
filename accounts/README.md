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