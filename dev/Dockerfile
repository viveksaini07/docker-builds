# Pull base image.
FROM ubuntu:15.04
ENV REFRESHED_AT 2015-11-06

# Install base packages
RUN apt-get update \
&& apt-get upgrade -y \
&& apt-get install -y curl


# Install nodejs packages
RUN apt-get install nodejs nodejs-legacy npm imagemagick git -y

# Will run in container
#RUN cd /opt && git clone -b v0.6.x https://github.com/NodeBB/NodeBB nodebb
#RUN cd /opt/nodebb && npm install

# Will create volume in docker run
#VOLUME /opt/nodebb

# Define working directory.
WORKDIR /opt/nodebb

# Expose ports
EXPOSE 80
EXPOSE 443
EXPOSE 4567

# Define default command.
CMD ["/bin/bash"]
