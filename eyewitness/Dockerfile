From kalilinux/kali-linux-docker:latest

# Adapted from https://github.com/znb/Docker/blob/master/EyeWitness/Dockerfile
MAINTAINER David Um "@dave5623"

RUN addgroup eyewitness
RUN useradd -r -g eyewitness -d /opt/eyewitness eyewitness

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
    git \
    libffi-dev \
    libssl-dev \
    python2.7 \
    python-pip \
    python-pyicu
RUN git clone https://github.com/ChrisTruncer/EyeWitness.git /opt/eyewitness
RUN pip install bs4
RUN /opt/eyewitness/setup/setup.sh
RUN chown eyewitness -R /opt/eyewitness
USER eyewitness
WORKDIR /opt/eyewitness


# RUN apt-get update && apt-get install -y cowsay fortune
# COPY entrypoint.sh /
# ENTRYPOINT ["/entrypoint.sh"]
