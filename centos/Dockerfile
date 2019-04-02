FROM centos:7
LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="include tools"

RUN \
    rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
  && yum install -y iproute wget unzip telnet curl

ENTRYPOINT [ "/bin/bash" ]
