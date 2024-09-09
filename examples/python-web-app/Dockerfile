FROM ubuntu:latest

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file and application files
COPY requirements.txt /app/
COPY devops /app/devops

# Install Python and pip, then install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip3 install --upgrade pip && \
    pip3 install -r requirements.txt

# Set the working directory to where manage.py is located
WORKDIR /app/devops

# Expose port 8000 for the Django application
EXPOSE 8000

# Define the default command to run the Django application
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]







