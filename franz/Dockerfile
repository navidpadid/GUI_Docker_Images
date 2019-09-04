FROM ubuntu-xfce-readyalpha:latest
LABEL maintainer="Navid Malek | navidmalek.blog.ir"

# installing franz
RUN sudo apt-get update && apt install -y wget
RUN wget https://github.com/meetfranz/franz/releases/download/v5.2.0/franz-5.2.0.tar.gz
RUN mkdir franz
RUN apt install -y libxss1 libgconf-2-4 libnss3 libasound2
RUN tar -xzvf franz-5.2.0.tar.gz -C franz/

# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
ADD . /app

ENV PROXY_SERVER=192.168.0.2
ENV PROXY_PORT=9150

COPY redsocks.conf /etc/redsocks.conf

ENTRYPOINT /bin/bash run.sh 
