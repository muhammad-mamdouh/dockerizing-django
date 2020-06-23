FROM python:3.7
MAINTAINER Mohamed Mamdouh

# Set the working directory of our app
WORKDIR /app

# Copy the app to the container's working directory
COPY ./app /app

# Install the requirements
RUN pip install -r requirements.txt

# Run the Django app server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
