# https://thingsboard.io/docs/user-guide/install/pe/ubuntu/
# https://docs.docker.com/develop/develop-images/dockerfile_best-practices/

FROM ubuntu:20.04

ARG TB_VERSION="3.3.2pe"

# Update OS and install prerequisites
RUN apt-get update && apt-get upgrade -y \
  && apt install -y openjdk-11-jdk wget \
  && rm -rf /var/lib/apt/lists/*

# Install Thingsboard
RUN wget -q "https://dist.thingsboard.io/thingsboard-$TB_VERSION.deb" -O thingsboard.deb  \
  && yes | dpkg -i thingsboard.deb
RUN /usr/share/thingsboard/bin/install/install.sh

USER thingsboard
CMD "/usr/share/thingsboard/bin/thingsboard.jar"
