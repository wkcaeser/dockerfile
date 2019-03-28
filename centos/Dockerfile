FROM centos:7
LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="iproute"

RUN \
    rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
  && yum install -y iproute

ENTRYPOINT [ "/bin/bash" ]
