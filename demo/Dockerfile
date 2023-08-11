# Use the official OpenJDK 8 image as the base image
FROM openjdk:8-jdk-alpine

# Set the working directory inside the container
WORKDIR /app

# Install wget and unzip
RUN apk update && apk add wget unzip

# Download and unzip the code from the GitHub repository
RUN wget https://github.com/Kriengg/springboot/archive/main.zip -O app.zip && \
    unzip app.zip && \
    mv springboot-main/* . && \
    rm -rf springboot-main app.zip

# Build the Spring Boot application
RUN ./mvnw clean install -DskipTests

# Expose the port that your Spring Boot application runs on
EXPOSE 8080

# Define the command to run your application
CMD ["java", "-jar", "target/demo-0.0.1-SNAPSHOT.war"]
