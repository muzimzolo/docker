FROM python:3.7.5-alpine

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

# In a Dockerfile, the LABEL instruction is used to add metadata to an image. 
# It allows you to provide information such as the image version, maintainer 
# details, description, and other relevant information.
# Syntax:
# LABEL <key>=<value> <key>=<value> ...

LABEL maintainer="Muzi Mzolo <meneer.mzolo@gmail.com>" \
      version="1.0" 

# The CMD instruction is used to specify the default command that should be executed when a container 
# is launched from the Docker image. The CMD instruction can be used only once in a Dockerfile, and 
# it defines the command and its arguments.

CMD flask run --host=0.0.0.0 --port=5000
