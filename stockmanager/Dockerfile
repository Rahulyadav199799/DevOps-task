# Use an official Java 8 runtime as a parent image
FROM openjdk:8-jdk-alpine

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install Maven and clean the target directory
RUN apk add --no-cache maven && \
    mvn clean

# Build the project using Maven and create the app.jar
RUN mvn package && \
    mv target/*.jar app.jar

# Expose port 8030 for the application
EXPOSE 8030

# Set the command to start the application
CMD ["java","-Djava.security.egd=file:/dev/./urandom","-jar","app.jar","server"]

