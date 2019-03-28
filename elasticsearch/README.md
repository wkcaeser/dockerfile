# elasticsearch cluster build docker-compose

docker-compose.yml用来构建es集群  
此集群3个节点  
采用自定义网络  
网络创建命令：

```  shell
docker network create --subnet 192.168.0.0/24 --gateway 192.168.0.1 wk-docker-cluster
```

elasticsearch-{1-3}.yml分别为三个节点的配置文件，基本相同