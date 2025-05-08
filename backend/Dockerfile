FROM openjdk:17-jdk-alpine

# Copy the WAR file from target directory to container
COPY /target/expenseTracker-0.0.1-SNAPSHOT.jar /app.jar

# Set the command to run the WAR file
ENTRYPOINT ["java", "-jar", "/app.jar"]

# Expose the port that your Spring Boot app will run on (8765)
EXPOSE 8080
