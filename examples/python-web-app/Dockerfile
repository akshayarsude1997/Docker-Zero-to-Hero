FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy the requirements file and the devops directory
COPY requirements.txt /app/
COPY devops /app/devops

# Update and install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install -r requirements.txt

# Set the working directory to devops
WORKDIR /app/devops

# Set the entry point for the container
ENTRYPOINT ["python3"]

# Set the default command to run the Django development server
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





