FROM centos:7
LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="centos include basic tools"

RUN \
    rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
    && yum install -y wget iproute telnet curl net-tools \
    && yum install -y unzip vim zip

ENTRYPOINT [ "/bin/bash" ]

# docker build -t wkcaeser/centos:v1 .