FROM wkcaeser/centos:jdk8

LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="kafka"

RUN wget -P /opt http://mirrors.tuna.tsinghua.edu.cn/apache/kafka/2.3.0/kafka_2.11-2.3.0.tgz \
    && tar -zxvf /opt/kafka_2.11-2.3.0.tgz -C /usr/local/ \
    && mv /usr/local/kafka_2.11-2.3.0 /usr/local/kafka \
    && rm -rf /opt/kafka_2.11-2.3.0.tgz

RUN echo "nohup /usr/local/kafka/bin/zookeeper-server-start.sh /usr/local/kafka/config/zookeeper.properties > /dev/null 2>&1 &" > /start.sh \
    && echo "/usr/local/kafka/bin/kafka-server-start.sh /usr/local/kafka/config/server.properties" >> /start.sh \
    && chmod +x /start.sh

EXPOSE 2181 9092

ENTRYPOINT ["/bin/bash", "/start.sh"]
