# docker-sentinel
alibaba sentinel


# TAGS

`1.8.6`,`latest`

`1.6.1`, `1.6.3`, 

# 端口
web端口 8718

api server : 8719

# 默认用户名和密码
sentinel/sentinel

# VOLUME

容器内日志目录：/opt/logs

# run

```shell
docker run --name sentinel -p 8718:8718 -v ./logs:/opt/logs thebizark/docker-sentinel
```

或

```shell
docker run -e JAVA_OPT_EXT='-Xmx1g' -e USERNAME="sentinel" -e PASSWORD="sentinel" -e SERVER_HOST="localhost" --name sentinel -p 8718:8718 thebizark/docker-sentinel
```
或

```shell
docker run --rm --name sentinel -p 8718:8718 thebizark/docker-sentinel
```

或

```shell
docker run --rm -e JAVA_OPT_EXT='-Xmx1g' --name sentinel -p 8718:8718 thebizark/docker-sentinel
```

# 官网

https://github.com/alibaba/Sentinel

新手指南

[https://github.com/alibaba/Sentinel/wiki/新手指南](https://github.com/alibaba/Sentinel/wiki/%E6%96%B0%E6%89%8B%E6%8C%87%E5%8D%97)






# 根据 Dockerfile 自己编译

编译镜像

```shell
docker build -t thebizark/docker-sentinel:1.6.1 --build-arg version=1.6.1 ./
```

启动容器
````SHELLL
docker run --rm --name sentinel -p 8718:8718 thebizark/docker-sentinel:1.6.1

或
docker run --rm -e JAVA_OPT_EXT="-Dserver.port=8718 -Dcsp.sentinel.dashboard.server=localhost:8718 -Dproject.name=sentinel-dashboard -Djava.security.egd=file:/dev/./urandom" --name sentinel -p 8718:8718 thebizark/docker-sentinel:1.6.1
````



# 其他k8s 使用案例

https://github.com/foxiswho/k8s-nacos-sentinel-rocketmq-zipkin-elasticsearch-redis-mysql
