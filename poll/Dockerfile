# Use an official Python image as the base image
FROM python:3.9

# Copy the application code and requirements file to the container's working directory
COPY ./requirements.txt /app/requirements.txt

# Set the working directory inside the container
WORKDIR /app

# Install the application's dependencies
RUN pip3 install -r requirements.txt

# copy every content from the local file to the image
COPY . /app

# Expose port 80 to run the application
EXPOSE 80

# Run the application using Flask
CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]