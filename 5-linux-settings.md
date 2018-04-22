# Linux 下 Shadowsocks 设置方法

## 1、GUI 客户端 （ 尚不支持 chacha20-ietf-poly1305 加密方式，请使用命令行客户端 ）

这里我们推荐使用 [shadowsocks-qt5](https://github.com/shadowsocks/shadowsocks-qt5)

1. [安装方法](https://github.com/shadowsocks/shadowsocks-qt5/wiki/%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97)
2. [使用方法](https://github.com/shadowsocks/shadowsocks-qt5/wiki/%E4%BD%BF%E7%94%A8%E6%89%8B%E5%86%8C)
3. [常见问题](https://github.com/shadowsocks/shadowsocks-qt5/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E5%92%8C%E8%A7%A3%E5%86%B3%E5%8A%9E%E6%B3%95)


## 2、命令行客户端
使用最新的 Python 版本或是 Shadowsocks-libev

### 1. 安装：
Python : https://github.com/shadowsocks/shadowsocks/tree/master#install  
Shadowsocks-libev: https://github.com/shadowsocks/shadowsocks-libev#installation

下面我们以 [Python 版](https://pypi.python.org/pypi/shadowsocks)的 Shadowsocks 为例


### 2. 设置 Shadowsocks 配置文件

创建一个 `/etc/shadowsocks.json` 文件，格式如下

```
{
    "server":"服务器IP或域名",
    "server_port":端口号,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"密码",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}
```

### 3、启动 Shadowsocks
Python 版客户端命令是 sslocal ， Shadowsocks-libev 客户端命令为 ss-local  

```
/usr/local/bin/sslocal -c /etc/shadowsocks.json -d start
```


### 4、安装 proxychains

这里以 Debian / Ubuntu 为例

```
sudo apt-get install proxychains
```

编辑 `/etc/proxychains.conf`

修改最后一行为

```
socks5 127.0.0.1 1080
```

接着我们就可以直接用

```
sudo proxychains apt-get xxxx
sudo proxychains wget xxxx
```

类似的命令使用 Shadowsocks 进行操作程序

### 5、 在应用程序内代理

您只需要将程式指定为 **socks v5** 的代理

服务器 127.0.0.1 端口 1080（应与 Shadowsocks 客户端的本地端口对应，默认为1080）

### 6、 关闭 Shadowsocks

在终端输入

```
lsof –i:1080
```

kill 相应 pid 即可

## 3、浏览器使用方法

1. [Firefox 浏览器设置教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/7-1-firefox-settings.md)
2. [Chrome 浏览器设置教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/7-2-chrome-settings.md)
