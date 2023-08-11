# Stage 1: Build the application
FROM maven:3.8.4-jdk-8 AS build
WORKDIR /app
COPY . .
RUN mvn clean install -DskipTests

# Stage 2: Create the final image
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.war app.war
EXPOSE 8080
CMD ["java", "-jar", "app.war"]
