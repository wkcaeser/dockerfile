FROM wkcaeser/centos:v1

LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="include dev c/c++ tools"

RUN \
    yum provides '*/applydeltarpm' \
    && yum install -y deltarpm \
    && yum install -y gcc gcc-c++ make

ENTRYPOINT [ "/bin/bash" ]

# docker build -t wkcaeser/centos:v2 .