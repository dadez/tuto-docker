# A Dockerfile is a simple text-file that contains a list of commands
# that the Docker client calls while creating an image.
# It's a simple way to automate the image creation process.
# The best part is that the commands you write in a Dockerfile are almost
# identical to their equivalent Linux commands. This means you don't really
# have to learn new syntax to create your own dockerfiles.

# Use ubuntu as base image, it will be downloaded automatically
FROM ubuntu:latest
MAINTAINER Jacques Celere "jacques.celere@gmail.com"

# Update and install python-3
RUN apt-get update && \
    apt-get install -y python3

# Create /home/www
RUN mkdir /home/www

# Set /home/www as WORKDIR
WORKDIR /home/www

# Copy index.html inside container, in /home/www
# NOTE: code could also be retrieved from git repository
ADD index.html /home/www/index.html

# Copy hello.py inside container, in /home/src
# NOTE: putting this command to the last line 
# would allow to rebuild only this layer if if hello.py is changed
ADD hello.py /home/src/hello.py

# Launch /home/src/hello.py at container startup 
# It will serve files located where it has been launch
EXPOSE 8000

CMD python3 /home/src/hello.py

