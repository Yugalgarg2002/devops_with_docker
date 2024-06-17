# Use Amazon Corretto as the base image for Java 8
FROM amazoncorretto:8

# Set the working directory inside the container
WORKDIR /app

# Install dos2unix
RUN yum install -y dos2unix

# Copy the Maven wrapper and the pom.xml file into the container
COPY .mvn .mvn
COPY mvnw pom.xml ./

# Convert line endings of the Maven wrapper script
RUN dos2unix mvnw

# Copy the source code into the container
COPY src ./src

# Give execute permission to the Maven wrapper
RUN chmod +x ./mvnw

# Build the project
RUN ./mvnw package

# Expose the application port
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
