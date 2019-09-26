# nginx tcp代理编译

## 添加用户

``` shell
groupadd nginx
useradd nginx -g nginx -s /bin/nologin -M
```

## 下载编译

``` shell
mkdir -pv /data/soft && cd /data/soft && wget http://nginx.org/download/nginx-1.14.2.tar.gz
tar -zxvf ./nginx-1.14.2.tar.gz -C /usr/local/ && cd /usr/local/nginx-1.14.2
./configure --prefix=/usr/local/nginx_tcp  --user=nginx  --group=nginx   --with-stream --without-http_rewrite_module --without-http_gzip_module && make && make install
```

## 配置文件

``` shell
# 文件路径： /usr/local/nginx/conf
user  nginx;
worker_processes  4;

error_log  /usr/local/nginx/logs/error.log;
error_log  /usr/local/nginx/logs/notice.log  notice;
error_log  /usr/local/nginx/logs/info.log  info;

pid        /usr/local/nginx/logs/nginx.pid;


events {
    worker_connections  65535;
}

stream {
     server {
           listen 16379 so_keepalive=on;
           proxy_pass tcp_6379_backend;
          # proxy_connect_timeout 1s;
          # proxy_timeout 3s;
          tcp_nodelay on;
     }
     upstream tcp_6379_backend {
          server 127.0.0.1:6379;
     }
}
```

## 测试及启动

``` shell
usr/local/nginx/sbin/nginx -t
/usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
```