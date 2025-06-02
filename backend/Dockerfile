FROM openjdk:17-jdk-alpine

# Create the directory where the profile images will be saved
RUN mkdir -p /app/uploads/user/profile

# Set working directory to /app so that relative paths in Spring Boot work correctly
WORKDIR /app

# Copy the jar file to the container
COPY /target/expenseTracker-0.0.1-SNAPSHOT.jar /app.jar

# Make sure Spring Boot has permission to write to the upload folder
RUN chmod -R 777 /app/uploads

# Expose the port Spring Boot runs on
EXPOSE 8080

# Run the app
ENTRYPOIN ["java", "-jar", "/app.jar"]
