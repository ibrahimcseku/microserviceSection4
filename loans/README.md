# STEP THAT NEED TO FOLLOW

# 1: Add packaging type in pom.xml file
	<packaging>jar</packaging>
	
# 2: Add the configuration like mention in below in project pom.xml file
	    <build>
	        <plugins>
	            <plugin>
	                <groupId>org.springframework.boot</groupId>
	                <artifactId>spring-boot-maven-plugin</artifactId>
	                <configuration>
	                	<image>
	                    	<name>ibrahimcseku/${project.artifactId}:s4</name>
	                    </image>
	                </configuration>
	            </plugin>
	        </plugins>
	    </build>
	      
# 3: Then run below maven command from the location where pom.xml file is present - 
	mvn spring-boot:build-image
	
# 4: Execute docker command to run the docker container based on the provided image name and port - 
	docker run -d -p 8090:8090 ibrahimcseku/loans:s4 

# To push an docker image or a repository to a remote registry (for my case I am pushing to docker hub remote repository)
	docker image push docker.io/ibrahimcseku/loans:s4
	
# To pull an image or a repository from a registry		
	docker image pull docker.io/ibrahimcseku/loans:s4