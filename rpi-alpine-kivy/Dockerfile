FROM bhuisgen/rpi-alpine-base-consul:latest
MAINTAINER Boris HUISGEN <bhuisgen@hbis.fr>

ENV LD_LIBRARY_PATH=/opt/vc/lib

COPY packages/*.apk /root/
RUN apk add --update py2-pip xclip && \
    apk add --allow-untrusted \
        /root/*.apk && \
    pip install kivy-garden && \
    rm -f /root/*.apk && \
    rm -rf /var/cache/apk/*

ENTRYPOINT ["/init"]
CMD []
