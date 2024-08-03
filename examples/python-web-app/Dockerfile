FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Install dependencies and Python
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    apt-get clean

# Create and activate a virtual environment
RUN python3 -m venv /venv

# Install Python packages in the virtual environment
RUN /venv/bin/pip install --upgrade pip
COPY requirements.txt /app/
RUN /venv/bin/pip install -r requirements.txt

# Copy the devops directory into the container
COPY devops /app/devops

# Set the working directory to devops
WORKDIR /app/devops

# Set environment variables to use the virtual environment
ENV PATH="/venv/bin:$PATH"

# Set the entry point for the container
ENTRYPOINT ["python3"]

# Set the default command to run the Django development server
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
