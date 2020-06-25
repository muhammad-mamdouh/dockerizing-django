# Base Python 3.6 image
FROM python:3.6

# Create and Set working directory
RUN mkdir /app
WORKDIR /app

# Add the current working directory code to the container's working directory
ADD . /app/

# Set default environment variables
ENV PYTHONUNBUFFERED 1
ENV LANG C.UTF-8
ENV DEBIAN_FRONTEND=noninteractive

# Set project specific environment variables
# Grab these via Python's os.environ, these are 100% optional here
#ENV PORT=8000

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
        tzdata \
        python3-setuptools \
        python3-pip \
        python3-dev \
        git && \
        apt-get clean && \
        rm -rf /var/lib/apt/lists/*

# Install environment dependencies
RUN pip3 install --upgrade pip
RUN pip3 install pipenv

# Install project dependencies
RUN pipenv install --skip-lock --system --dev

#EXPOSE 8888
#CMD gunicorn djgunicorn.wsgi:application --bind 0.0.0.0:$PORT
