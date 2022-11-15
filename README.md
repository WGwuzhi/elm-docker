# elm-docker
 饿了么工具docker
 
 [![Docker Image Publish](https://github.com/zelang/elm-docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/zelang/elm-docker/actions/workflows/docker-publish.yml)
 
 工具使用说明：[elm-release](https://github.com/zelang/elm-release)
 
一键安装：
```shell
bash <(wget --no-check-certificate -qO- 'https://ghproxy.com/https://raw.githubusercontent.com/zelang/elm-docker/main/elmtool.sh')
```

或

```shell
docker run -dit \
  -v /etc/elmtool/config.ini:/etc/elmtool/config.ini \
  --name elmtool \
  --hostname elmtool \
  --restart unless-stopped \
  marisn/elmtool:latest
```
手动下载`config.ini`然后修改`/etc/elmtool/config.ini`中配置
重启：`docker restart elmtool`
----
手动安装：
```shell
mkdir -p /etc/elmtool && chmod +x /etc/elmtool && cd /etc/elmtool
wget https://ghproxy.com/https://raw.githubusercontent.com/zelang/elm-docker/main/docker-compose.yml -O /etc/elmtool/docker-compose.yml
wget https://ghproxy.com/https://raw.githubusercontent.com/zelang/elm-docker/main/config.ini -O /etc/elmtool/config.ini
docker-compose pull
docker-compose up -d --force-recreate
```

使用说明：

1. 手动安装需要预装docker和docker-compose环境
2. 使用一键脚本安装或者手动安装后，需要先执行 `docker stop elmtool` 停止docker运行
3. 然后修改`/etc/elmtool/config.ini`配置文件
4. 再执行命令：`cd /etc/elmtool && docker start elmtool`
