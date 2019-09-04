FROM ubuntu-xfce-readyalpha:latest
LABEL maintainer="Navid Malek | navidmalek.blog.ir"

# installing MPV
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:mc3man/mpv-tests && apt update
RUN apt-get install -y mpv



# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
ADD . /app

ENV PROXY_SERVER=192.168.0.2
ENV PROXY_PORT=9150

COPY redsocks.conf /etc/redsocks.conf

ENTRYPOINT /bin/bash run.sh 
