# Use the latest Ubuntu image
FROM ubuntu:latest

# Update APT and install Python3 and pip3
RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y python3 python3-pip \
    && rm -rf /var/lib/apt/lists/*

# Fix the "EXTERNALLY-MANAGED" error
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask and Flask-CORS
RUN pip3 install --no-cache-dir flask flask-cors

# Set the working directory
WORKDIR /app

# Copy the api.py file into the container
COPY ./api.py /app/api.py

# Expose port 5252
EXPOSE 5252

# Set the default command to run the Flask server
CMD ["python3", "api.py"]
