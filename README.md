# elm-docker
 饿了么工具docker
 
 [![Docker Image Publish](https://github.com/zelang/elm-docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/zelang/elm-docker/actions/workflows/docker-publish.yml)
 
 工具使用说明：[elm-release](https://github.com/zelang/elm-release)
 
### Docker使用步骤：

#### 步骤一

- 手动下载本网页中的`config.ini`到`/etc/elmtool/`目录下，然后修改`/etc/elmtool/config.ini`中配置，如果没有此目录，先手动创建

#### 步骤二

- 确认`/etc/elmtool/`目录下的配置文件已修改完毕，再执行以下命令：

```shell
docker run -dit \
  -v /etc/elmtool/config.ini:/etc/elmtool/config.ini \
  --name elmtool \
  --restart unless-stopped \
  marisn/elmtool:latest
```

### 一些小提示：
 1. 查看日志：`docker logs elmtool`
 2. 重启：`docker restart elmtool`
 3. 停止并删除：`docker stop elmtool && docker rm elmtool`
 4. 更新：
  - `docker stop elmtool && docker rm elmtool`
  - `docker rmi marisn/elmtool`
  - `docker pull marisn/elmtool`
  - 执行步骤二