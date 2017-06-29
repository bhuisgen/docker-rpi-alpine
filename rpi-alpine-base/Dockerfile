FROM armhf/alpine:3.5
MAINTAINER Boris HUISGEN <bhuisgen@hbis.fr>

ARG BUILD_ARCH=x86_64

ENV S6OVERLAY_VERSION=v1.19.1.1 \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=1 \
    LANG=en_US.UTF-8 \
    LC_ALL=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    TERM=xterm

COPY packages/build/${BUILD_ARCH}/*.apk /root/
RUN apk update && \
    apk upgrade && \
    apk add --allow-untrusted \
        bash bind-tools ca-certificates curl jq tar \
        /root/*.apk && \
    curl -sSL https://github.com/just-containers/s6-overlay/releases/download/${S6OVERLAY_VERSION}/s6-overlay-armhf.tar.gz | tar xz -C / && \
    apk del tar && \
    rm -f /root/*.apk && \
    rm -rf /var/cache/apk/*

COPY rootfs/ /
