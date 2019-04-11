# Dockerfile for Filebeat

# Alpine OS 3.4
# http://dl-cdn.alpinelinux.org/alpine/v3.4/community/x86_64/
FROM wkcaeser/centos:v2

LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="filebeat 6.4.2"

ENV FILEBEAT_VERSION=6.4.2

RUN \
    curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz \
 && tar xzvf filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz -C / --strip-components=1 \
 && rm -rf filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz 


ENTRYPOINT ["/filebeat", "-c", "/filebeat.yml"]

# docker build -t "wkcaeser/filebeat:6.4.2" .
# docker run --rm -it -v filebeat.yml:/filebeat.yml --net=wk-docker-cluster --ip=192.168.0.11 wkcaeser/filebeat:6.4.2
# docker run --rm -it -v /data/projects/my_projects/dockerfile/filebeat/filebeat.yml:/filebeat.yml  -v ~/Desktop/logs:/data/var/log --net=wk-docker-cluster --ip=192.168.0.11 wkcaeser/filebeat:6.4.2