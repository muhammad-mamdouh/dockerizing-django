FROM python:3.7
MAINTAINER Mohamed Mamdouh

# Set the working directory of our app
WORKDIR /app

# Copy the app to the container's working directory
COPY ./app /app

# Install the requirements
RUN pip install -r requirements.txt

# Copy and run the entrypoint script
COPY ./docker/app/entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
