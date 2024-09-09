# Use an official Ubuntu image with a tag
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy application files
COPY requirements.txt /app/
COPY devops /app/devops/

# Install Python, pip, and virtual environment package
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /venv && \
    /venv/bin/pip install --upgrade pip && \
    /venv/bin/pip install -r requirements.txt

# Set the working directory to the location of manage.py
WORKDIR /app/devops

# Expose port 8000
EXPOSE 8000

# Use the virtual environment to run the Django application
ENTRYPOINT ["/venv/bin/python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]









