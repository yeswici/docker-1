# Usage: Follow the steps in ../README.md.

FROM ubuntu:16.04

RUN apt-get update ; apt-get -y upgrade ; apt-get -y autoclean
RUN apt-get -y install git python3-pip python3-dev
RUN pip3 install buildbot buildbot-slave

# Configuration
RUN adduser --disabled-password --gecos "Continuese Integration" master
WORKDIR /home/master

COPY master.cfg run.sh /home/master/
RUN chown master:master run.sh master.cfg
USER master

# Defaults
## For communicating with buildslaves
EXPOSE 9989
## For webpage
EXPOSE 8010

CMD bash
