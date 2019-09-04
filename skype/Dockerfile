FROM ubuntu-xfce-readyalpha:latest
LABEL maintainer="Navid Malek | navidmalek.blog.ir"

# installing Skype
RUN apt-get update && apt-get install -y \
	apt-transport-https \
	ca-certificates \
	curl \
	gnupg \
	procps \
	--no-install-recommends
	
RUN curl -sSL https://repo.skype.com/data/SKYPE-GPG-KEY | apt-key add -
RUN echo "deb [arch=amd64] https://repo.skype.com/deb stable main" > /etc/apt/sources.list.d/skype.list

RUN apt-get update && apt-get -y install \
	skypeforlinux \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*


# Set the working directory to /app
WORKDIR /app
# Copy the current directory contents into the container at /app
ADD . /app

ENV PROXY_SERVER=192.168.0.2
ENV PROXY_PORT=9150

COPY redsocks.conf /etc/redsocks.conf

ENTRYPOINT /bin/bash run.sh 
