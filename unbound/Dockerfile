ARG BUILD_FROM
FROM $BUILD_FROM
#### FROM ghcr.io/home-assistant/base:latest
RUN apk update
RUN apk upgrade
RUN apk add --no-cache unbound
RUN wget -O /etc/unbound/root.hints https://www.internic.net/domain/named.cache
RUN unbound-anchor
COPY unbound.conf /etc/unbound/unbound.conf
CMD ["/usr/sbin/unbound", "-d", "-vvv"]
