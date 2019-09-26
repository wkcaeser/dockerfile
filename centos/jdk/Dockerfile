FROM wkcaeser/centos:v2

LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="jdk 1.8_221"

ADD jdk-8u221-linux-x64.rpm /opt

RUN \
    rpm -ivh /opt/jdk-8u221-linux-x64.rpm \
    && rm -f /opt/jdk-8u221-linux-x64.rpm

ENTRYPOINT [ "/bin/bash" ]

# docker build -t wkcaeser/centos:jdk8 .
