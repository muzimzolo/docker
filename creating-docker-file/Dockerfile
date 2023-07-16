FROM python:3.7.5-alpine

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt

# To install Python packages in a Dockerfile, you can use the RUN instruction along with the pip command
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

# To build the image run the build command and supply a name i.e. docker image build -t web1 .
# -t web1 gives our image a tag so that our image has a name

# To inspect our image run the inspect command i.e. docker image inspect web1

# To version your image rebuild it with a tag: docker image build -t web1:1.0 .

# To remove the versioned image run: docker image rm web1:1.0

# To push the image to docker hub: 
# docker login & follow the prompts
# docker image tag web1 <username/<image-name:<tag>> i.e. docker image tag web1 muzidebugger/web1:latest
# verify it by running docker image ls
# Push the image using docker image push <username/<image-name:<tag>> i.e docker image push muzidebugger/web1:latest
# Remove the image using docker image rm -f <image-id>
# pull the image from the repository: docker pull <username>/<image> i.e. docker pull muzidebugger/web1:latest
# Confirm that it was downloaded: docker image ls
# To rename the image by removing the docker hub username tag: docker tag muzidebugger/web1 web1
# To run a container: docker container run -it -p 5000:5000 -e FLASK_APP=app.py web1
# docker container run -it -p <docker host><app port> -e <><app name> <image name>
# "e" stands for environment variable. You can pass multiple e flags if you want to run in multiple environment variables
# app.py relates to the flask app that we created - app.py
# Run our app on http://localhost:5000
# To remove the image: docker container run -it --rm --name web1 -p 5000:5000 -e FLASK_APP=app.py web1 
# Docker logs in real time: docker container logs -f <image> i.e docker container logs -f web1