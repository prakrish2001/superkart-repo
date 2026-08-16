# Use a minimal Python 3.9 image as the base
FROM python:3.9-slim

# Set the working directory inside the container to /app
WORKDIR /app

# Copy the actual Python application code (streamlit app.py) to our working directory
COPY . .

# Install Python dependencies listed in requirements.txt
RUN pip3 install -r requirements.txt

# Define the command to run the Streamlit app,
# binding to all network interfaces on port 8501 and disabling XSRF protection.
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0", "--server.enableXsrfProtection=false"]

# NOTE: Disable XSRF protection for easier external access in order to make batch predictions
