ARG BUILD_FROM=hassioaddons/debian-base:3.2.0
FROM ${BUILD_FROM}

#FROM docker.elastic.co/beats/filebeat:6.8.9

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN apt-get update \
  && apt-get install -y curl \
  && curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-6.8.9-amd64.deb \
  && dpkg -i filebeat-6.8.9-amd64.deb \
  && apt-get install -y filebeat-oss

COPY rootfs /

# Labels
LABEL \
    io.hass.name="Filebeat" \
    io.hass.description="Filebeat add-on by Robert" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Robert Lech <robertdlech@gmail.com>" \
    org.opencontainers.image.title="Filebeat" \
    org.opencontainers.image.description="Filebeat add-on by Robert" \
    org.opencontainers.image.vendor="Robert" \
    org.opencontainers.image.authors="Robert Lech <robertdlech@gmail.com>" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://addons.community" \
    org.opencontainers.image.source="https://github.com/Robberbob/addon-filebeat" \
    org.opencontainers.image.documentation="https://github.com/Robberbob/addon-filebeat/blob/master/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
