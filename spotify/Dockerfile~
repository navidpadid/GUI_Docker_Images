FROM ubuntu-xfce-readyalpha:latest
LABEL maintainer="Navid Malek | navidmalek.blog.ir"

# installing spotify
RUN apt update && apt install -y gnupg2
RUN echo "deb http://repository.spotify.com stable non-free">> /etc/apt/sources.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90 2EBF997C15BDA244B6EBF5D84773BD5E130D1D45
RUN sudo apt-get update && sudo apt-get install -y spotify-client


# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
ADD . /app

ENV PROXY_SERVER=192.168.0.2
ENV PROXY_PORT=9150

COPY redsocks.conf /etc/redsocks.conf

ENTRYPOINT /bin/bash run.sh 
