ARG BUILD_FROM=hassioaddons/debian-base:3.2.0
FROM ${BUILD_FROM}

#FROM docker.elastic.co/beats/filebeat:6.8.9

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN apt update \
  && curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-6.8.9-amd64.deb \
  && dpkg -i filebeat-6.8.9-amd64.deb \
  && apt install -y filebeat-oss

COPY filebeat.yml /etc/filebeat/filebeat.yml
USER root
RUN chown root:filebeat /etc/filebeat/filebeat.yml
USER filebeat
