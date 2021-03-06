# webssh
![](https://img.shields.io/github/v/release/Jrohy/webssh.svg) 
![](https://img.shields.io/docker/pulls/jrohy/webssh.svg) 
[![Downloads](https://img.shields.io/github/downloads/Jrohy/webssh/total.svg)](https://img.shields.io/github/downloads/Jrohy/webssh/total.svg) 
[![License](https://img.shields.io/badge/license-GPL%20V3-blue.svg?longCache=true)](https://www.gnu.org/licenses/gpl-3.0.en.html)   
简易在线ssh和sftp工具, 可在线敲命令和上传下载文件

## 运行截图
![avatar](asset/1.png)
![avatar](asset/2.png)

## 命令行
```
Usage of ./webssh_linux_amd64:
  -p int
        服务运行端口 (default 5032)
  -t int
        ssh连接超时时间(min) (default 60)
```

## 原理
```
+---------+     http     +--------+    ssh    +-----------+
| browser | <==========> | webssh | <=======> | ssh server|
+---------+   websocket  +--------+    ssh    +-----------+
```

## 运行
下载release里不同平台的包来执行即可

docker运行:
```
docker run -d -p 5032:5032 --log-driver json-file --log-opt max-file=1 --log-opt max-size=100m --restart always --name webssh -e TZ=Asia/Shanghai jrohy/webssh
```
