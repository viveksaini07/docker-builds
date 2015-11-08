# Pull base image.
FROM ubuntu:15.04
ENV REFRESHED_AT 2015-11-06

# Install base packages
RUN apt-get update \
&& apt-get upgrade -y \
&& apt-get install -y curl

# Install mongodb
WORKDIR /usr/local/

RUN curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.0.7.tgz  \
&& tar -zxvf mongodb-linux-x86_64-3.0.7.tgz \
&& ln -s mongodb-linux-x86_64-3.0.7 mongodb \
&& mkdir -p /data/db

RUN mkdir -p /data/log

ADD ["rs.conf","/usr/local/mongodb/rs.conf"]

# Define mountable directories.
VOLUME ["/data/db"]

# Expose ports.
#   - 27017: process
EXPOSE 27017

## export path
ENV PATH /usr/local/mongodb/bin/:$PATH

#entrypoint
CMD ["mongod","--config","/usr/local/mongodb/rs.conf"]
