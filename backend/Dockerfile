# Use a minimal Python 3.9 image as the base
FROM python:3.9-slim

# Set the working directory inside the container to /app/backend
WORKDIR /app/backend

# Copy the entire contents of the local 'backend_files' directory into '/app/backend_files' in the container
# This preserves the directory structure required by the model loading path.
COPY . /app/backend_files/

# Copy the actual Python application code to our working directory (which is /app/backend)
COPY . .

# Install Python dependencies listed in requirements.txt without caching and upgrade pip
RUN pip install --no-cache-dir --upgrade -r requirements.txt

# Define the command to start the application using Gunicorn, binding to all network interfaces on port 7860
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "app:superkart_api"]
