# STEP THAT NEED TO FOLLOW TO BUILD DOCKER IMAGE WITH GOOGLE JIB
	reference url - https://github.com/GoogleContainerTools/jib/tree/master/jib-maven-plugin

# 1: Add packaging type in pom.xml file
	<packaging>jar</packaging>

# 2: Add the configuration like mention in below in project pom.xml file
	<plugin>
        <groupId>com.google.cloud.tools</groupId>
        <artifactId>jib-maven-plugin</artifactId>
        <version>3.4.6</version>
        <configuration>
          <to>
            <image>ibrahimcseku/${project.artifactId}:s4</image>
          </to>
        </configuration>
 	</plugin>	    
	      
# 3: Then run below maven command from the location where pom.xml file is present - 
	mvn compile jib:dockerBuild

# 4: Execute docker command to run the docker container based on the provided image name and port - 
	docker run -d -p 9000:9000 ibrahimcseku/cards:s4 
	