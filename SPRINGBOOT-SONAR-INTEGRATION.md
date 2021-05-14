# Integration Spring Boot Application Source Code with Sonarqube

While our software projects evolve, they must be in good quality. Thus, we apply practices like TDD and pair programming.
Besides, we can benefit from quality measurement tools like Sonarqube. Above all, in this post, we are going to check out 
how we can configure Spring boot 2.x.x with Sonarqube.

## Tools

Below components are used for the sample project:
1. [Spring Boot 2.x.x](https://start.spring.io/)
2. [Sonarqube (community edition)](https://www.sonarqube.org/)
3. [sonar-maven-plugin 3.9.0.2155](https://mvnrepository.com/artifact/org.sonarsource.scanner.maven/sonar-maven-plugin)
4. [maven-surefire-plugin 3.0.0-M5](https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-surefire-plugin)
5. [jacoco-maven-plugin 0.8.7](https://mvnrepository.com/artifact/org.jacoco/jacoco-maven-plugin)

## Maven Plugin Details

Before starting the example, let’s learn what are these plugins for.

### Sonar Maven Plugin

This plugin provides a Sonar Scanner for Maven. When we run the plugin’s goal with "sonar:sonar", the code quality 
measurement processes locally and sends the report to the configured Sonarqube server.

### Maven Surefire Plugin

This plugin is special for maven. Even though you don’t include it into the project, when you run the tests with maven 
it will download and run the tests with this plugin. Also, you can specify running order, test class name patterns 
to include, etc... After running the tests, the Surefire plugin generates reports like below:

### Jacoco Maven Plugin

Jacoco plugin is used to calculate the test coverage ratio. With the latest version of Sonarqube, the coverage is 
only generated via this plugin. Thus, you cannot get the coverage info without Jacoco anymore.
