# SRS-Streaming-Server
从0搭建自己的流媒体服务器，用于本地视频/摄像头推流、拉流

# 1.使用finalshell连接阿里云服务器
[使用finshell连接阿里云服务器参考教程](https://github.com/shizishen/SRS-Streaming-Server/tree/master)
# 2.在阿里云服务器中部署SRS流媒体服务器


## 2.1.先用Docker启动SRS:
```
docker run --rm -it -p 1935:1935 -p 1985:1985 -p 8080:8080 \
    registry.cn-hangzhou.aliyuncs.com/ossrs/srs:5
```
![Screenshot_20231219_114039](https://github.com/shizishen/SRS-Streaming-Server/assets/85082613/838af85f-243b-4c42-a0ea-0d2a42f06cf7)=300x200
## 2.2.在自己电脑上使用ffmpeg的docker推流，或者也可以使用obs软件推流
（注意：服务器的对应端口一定要打开，很多教程没有说明，第一次使用服务器不知道，很坑，去阿里云获或者腾讯云的防火墙设置里打开1935的端口，因为按照该教程，默认使用的是器1935的端口）
```
docker run --rm -it registry.cn-hangzhou.aliyuncs.com/ossrs/srs:encoder \
  ffmpeg -stream_loop -1 -re -i doc/source.flv -c copy \
    -f flv rtmp://host.docker.internal/live/livestream
```
或者也可以使用ffmpeg直接推流（这个需要自己下载编译ffmpeg，其中./doc/source.flv 指定自己的文件，localhost指定自己服务器的ip）
```
ffmpeg -re -i ./doc/source.flv -c copy -f flv rtmp://localhost/live/livestream
```
## 2.3.使用浏览器拉流：
localhost替换成自己服务器的ip
```
RTMP (by VLC): rtmp://localhost/live/livestream  
H5(HTTP-FLV): http://localhost:8080/live/livestream.flv  
H5(HLS): http://localhost:8080/live/livestream.m3u8  
```


感谢以下博客：  
[1.使用docker镜像部署SRS](https://ossrs.net/lts/zh-cn/docs/v6/doc/getting-started)  
[2.一个非常好的docker使用教程](https://docker.easydoc.net/doc/81170005/cCewZWoN/lTKfePfP)
