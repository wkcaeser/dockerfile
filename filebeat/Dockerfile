# Dockerfile for Filebeat

# Build with:
# docker build -t "wkcaeser/filebeat:6.4.2" .

# Alpine OS 3.4
# http://dl-cdn.alpinelinux.org/alpine/v3.4/community/x86_64/
FROM alpine:3.4

LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="filebeat 6.4.2"

ENV FILEBEAT_VERSION=6.4.2

RUN \
    curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz \
 && tar xzvf filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz -C / --strip-components=1 \
 && rm -rf filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz 


ENTRYPOINT ["/docker-entrypoint.sh", "-c", "/filebeat.yml"]