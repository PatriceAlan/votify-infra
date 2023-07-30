# First Stage - Compilation
FROM maven:3.5-jdk-8-alpine AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the application files to the container's working directory
COPY pom.xml /app/
COPY src /app/src/

# Resolve application dependencies
RUN mvn dependency:resolve

# Package the Worker application
RUN mvn package

# Second Stage - Run
FROM openjdk:8-jre-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy the compiled Worker application from the first stage
COPY --from=builder /app/target/worker-jar-with-dependencies.jar /app/

# Set any necessary environment variables for the application
# For example, you can use ENV to set connection information
# ENV VARIABLE_NAME=value

# Run the Worker application
CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
