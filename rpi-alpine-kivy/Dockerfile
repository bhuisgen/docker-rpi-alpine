FROM bhuisgen/rpi-alpine-base-consul:latest
MAINTAINER Boris HUISGEN <bhuisgen@hbis.fr>

ENV LD_LIBRARY_PATH=/opt/vc/lib

COPY packages/*.apk /root/
RUN apk add --update --allow-untrusted \
        xclip \
        /root/*.apk && \
    rm -f /root/*.apk && \
    rm -rf /var/cache/apk/*

ENTRYPOINT ["/init"]
CMD []
