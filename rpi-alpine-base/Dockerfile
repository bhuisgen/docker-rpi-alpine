FROM arm32v6/alpine:3.7
LABEL maintainer="Boris HUISGEN <bhuisgen@hbis.fr>"

ARG BUILD_ARCH=x86_64

ENV S6OVERLAY_VERSION=1.21.4.0 \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=1

COPY packages/build/${BUILD_ARCH}/*.apk /root/
RUN apk update && \
    apk upgrade && \
    apk add bash bind-tools ca-certificates curl jq tar && \
    apk add --allow-untrusted \
        /root/*.apk && \
    curl -sSL https://github.com/just-containers/s6-overlay/releases/download/v${S6OVERLAY_VERSION}/s6-overlay-armhf.tar.gz | \
        tar xz -C / && \
    apk del tar && \
    rm -f /root/*.apk && \
    rm -rf /var/cache/apk/*

COPY rootfs/ /
