# POC Spring Cloud Configurations 
## Steps
- Create a Git Repository
   * Create a Git repository where property files will be stored.
   * Ensure the repository is accessible and permissions are set up accordingly.
- Configure Spring Boot Application
   * Create a Spring Boot application that will function as the Spring Cloud Config Server.
   * Add the following dependency to the pom.xml file:
- <dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-config-server</artifactId>
   </dependency>
- Configure the application properties
    spring.cloud.config.server.git.uri=<git-repository-url>
    spring.cloud.config.server.git.username=<git-username>
    spring.cloud.config.server.git.password=<git-password>
  * Replace <git-repository-url>, <git-username>, and <git-password> with the appropriate values.

- Build and Run the Application
   * Build the Spring Boot application using Maven.
   * Run the application or deploy it to your preferred environment.
- Verify Configuration Server Setup
   * Access the Spring Cloud Config Server endpoint to verify the setup.
   * Ensure that the configuration properties stored in the Git repository are accessible through the Config Server API.
- Configure Spring Boot Application
   * Create a Spring Boot application that will function as the Spring Cloud Config Client.
   * Add the following dependency to the pom.xml file:
    <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-config</artifactId>
    </dependency>
- Configure the application properties
    spring.config.import=optional:configserver:http://localhost:8080/
- Build and Run the Application
   * Build the Spring Boot application using Maven.
   * Run the application or deploy it to your preferred environment.
- Verify Configuration Client Setup
   * Access the Spring Cloud Config Client endpoint to verify the setup.
- Refresh the scope
   * After marking the chnages in git properties file, hit the endpoint
        - http://localhost:8082/poc/actuator/refresh (To refresh the scope)
  
