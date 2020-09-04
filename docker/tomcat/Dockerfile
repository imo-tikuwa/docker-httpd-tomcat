FROM alpine:3.10

ARG TOMCAT_VERSION=7.0.105
ARG TOMCAT_ARCHIVE=apache-tomcat-${TOMCAT_VERSION}

RUN alias ll='ls -l --color=auto'
RUN apk update \
    && apk --no-cache add curl openjdk11-jre-headless \
    && rm -rf /var/cache/apk/*

# tomcatインストール
WORKDIR /usr/local
RUN curl --insecure -OL https://ftp.kddi-research.jp/infosystems/apache/tomcat/tomcat-7/v$TOMCAT_VERSION/bin/$TOMCAT_ARCHIVE.tar.gz
RUN tar -zxvf $TOMCAT_ARCHIVE.tar.gz
RUN ln -s $TOMCAT_ARCHIVE tomcat

