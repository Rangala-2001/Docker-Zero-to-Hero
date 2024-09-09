# Use the official Python image as a parent image
FROM python:3

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file and install Python packages
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application files into the container
COPY . /app/devops

# Set the working directory to the location where manage.py is
WORKDIR /app/devops

# Expose port 8000 for the Django application
EXPOSE 8000

# Define the default command to run the Django application
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]





