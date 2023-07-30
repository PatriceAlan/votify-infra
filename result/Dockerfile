# Use an official Node.js version 12 Alpine image as the base image
FROM node:12-alpine

# Copy the application files to the container's working directory
COPY . /app

# Set the working directory inside the container
WORKDIR /app

# Install the application's dependencies
RUN npm install

# Expose port 80 to run the application
EXPOSE 80

# Run the application
CMD ["node", "server.js"]

