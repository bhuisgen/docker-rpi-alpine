FROM bhuisgen/rpi-alpine-base-consul:latest
LABEL maintainer="Boris HUISGEN <bhuisgen@hbis.fr>"

ENV JENKINS_HOME=/home/jenkins

RUN mkdir ${JENKINS_HOME} && \
    addgroup -S jenkins && \
    adduser -S -D -g "" -G jenkins -s /bin/sh -h ${JENKINS_HOME} jenkins && \
    chown jenkins:jenkins ${JENKINS_HOME}

RUN apk add --update git docker openjdk8-jre openssh && \
    rm -rf /var/cache/apk/*

COPY rootfs/ /

ENTRYPOINT ["/init"]
CMD []

EXPOSE 22
VOLUME ["/home/jenkins"]
