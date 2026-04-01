ARG BUILD_FROM
### ARG BUILD_FROM=ghcr.io/hassio-addons/base:latest
FROM $BUILD_FROM
#### FROM ghcr.io/home-assistant/base:latest
RUN apk update
RUN apk upgrade
RUN apk add --no-cache unbound
RUN wget -O /etc/unbound/root.hints https://www.internic.net/domain/named.cache
RUN unbound-anchor
COPY unbound.conf /etc/unbound/unbound.conf
CMD ["/usr/sbin/unbound", "-ddd", "-vvv"]

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="migo1271" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    # org.opencontainers.image.vendor="Home Assistant Community Add-ons" \
    org.opencontainers.image.authors="migo1271" \
    org.opencontainers.image.licenses="MIT" \
    # org.opencontainers.image.url="https://addons.community" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
