FROM ubuntu-xfce-readyalpha:latest
LABEL maintainer="Navid Malek | navidmalek.blog.ir"

# installing rambox
RUN sudo apt-get update && apt install -y wget
RUN wget https://github.com/ramboxapp/community-edition/releases/download/0.6.9/Rambox-0.6.9-linux-amd64.deb
RUN apt install -y gconf2 libappindicator1 libnss3 libxss1
RUN apt --fix-broken install -y
RUN dpkg -i Rambox-0.6.9-linux-amd64.deb 

# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
ADD . /app

ENV PROXY_SERVER=192.168.0.2
ENV PROXY_PORT=9150

COPY redsocks.conf /etc/redsocks.conf

ENTRYPOINT /bin/bash run.sh 
