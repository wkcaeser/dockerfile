FROM wkcaeser/centos:v2
LABEL maintainer="wkCaeser" \
        email="wkCaeser@gmail.com" \
        description="nginx proxies tcp"

RUN \
    groupadd nginx && useradd nginx -g nginx -s /bin/nologin -M \
    && mkdir -pv /data/soft && cd /data/soft && wget http://nginx.org/download/nginx-1.14.2.tar.gz \
    && tar -zxvf ./nginx-1.14.2.tar.gz -C /usr/local/ && cd /usr/local/nginx-1.14.2 \
    && ./configure --prefix=/usr/local/nginx  --user=nginx  --group=nginx   --with-stream --without-http_rewrite_module --without-http_gzip_module \
    && make && make install \
#     && rm -f /usr/local/nginx/conf/nginx.conf \
    && rm -rf /data/soft \
    && rm -rf /usr/local/nginx-1.14.2

ADD nginx.conf /usr/local/nginx/conf/

EXPOSE 80

ENTRYPOINT [ "/usr/local/nginx/sbin/nginx", "-g", "daemon off;" ]