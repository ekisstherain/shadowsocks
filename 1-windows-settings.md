# Windows 下 Shadowsocks 设置方法

## 1、下载客户端

我们推荐您使用最新版本的客户端，点击[这里](https://github.com/shadowsocks/shadowsocks-windows/releases)下载最新的客户端

## 2、安装 .NET Framework

一般 Windows 10 已经自带，不需要额外安装，如果您的系统版本略旧，请在[这里](https://www.microsoft.com/zh-tw/download/details.aspx?id=53345)下载适用于 Windows 7 SP1、Windows 8.1、Windows Server 2008 R2 SP1、Windows Server 2012 及 Windows Server 2012 R2 的 Microsoft .NET Framework 4.6.2 (Web 安装程式)

## 3、解压 Shadowsocks 客户端

阁下完成下载后，可以在熟悉的位置创建一个便於找到的文件夹，在本文中我们尝试在桌面新建名为 `Shadowsocks` 的文件夹，之后请打开下载的 Shadowsocks 客户端文件 请选中其中`Shadowsocks.exe`文件拖动至刚刚新建的 Shadowsocks 文件夹，并双击运行 `Shadowsocks.exe`

![](https://ooo.0o0.ooo/2017/05/22/5922f811318ad.png)

## 4、配置 Shadowsocks 账号

登陆我们的 [Portal](https://portal.shadowsocks.to/)，在 服务 > [我的服务](https://portal.shadowsocks.to/clientarea.php?action=services) 页面中，进入您的产品信息页面，点击配置文件下载，即可得到一个 `gui-config.json` 文件

![](https://i.loli.net/2017/11/02/59fa820b000dd.png)

![](https://ooo.0o0.ooo/2017/01/04/586d06f3a425b.png)

您也可以通过二维码方式单独增加节点，在您右下方状态栏 Shadowsocks 图标右键-服务器-扫描屏幕上的二维码

*提示*: 此二维码同样适应於其他客户端

![](https://ooo.0o0.ooo/2017/05/22/5922fa22e6d8e.png)

将您的 `gui-config.json` 文件放在 `shadowsocks.exe` 同一个文件夹下即可

双击您右下方状态栏的 Shadowsocks 图标，即可看到您的节点信息和账号已经自动配置完成

## 5、配置系统代理

右击您右下方状态栏的 Shadowsocks 图标，勾选 启用系统代理 并选择 Pac 模式

![](https://ooo.0o0.ooo/2017/05/22/5922fe379b134.png)

如果使用`PAC 模式` 无法访问网站，请前往[这里](https://portal.shadowsocks.to/dl.php?type=d&id=14) 下载 pac 配置文件，将 `pac.txt` 放在与shadowsocks.exe 相同的目录文件夹下即可

注意事项:

1. 负载均衡模式高可用模式与在于分散流量和提高可用性上，对于速度的提升没有帮助，如果对某一节点的连接质量较佳，推荐直接选中该服务器
2. 推荐使用 `PAC模式`，该模式可以实现自动代理，及没被屏蔽的网站的流量不会经过代理。但是在 `Shadowsocks Win 2.x` 版本中因内置的 GFWList 链接已失效，导致 PAC 规则无法更新，您可以从选择从本站下载 PAC 文件，或者遇到无法代理的网站时，通过编辑本地 PAC 文件，自己添加规则不包含但自己所需要代理的网站
3. `全局模式`表示基本上电脑内所有的流量都会经过代理，不推荐日常使用，因为很容易导致您的国内网站的流量以及迅雷等下载网站流量经过代理造成我们收到 ISP 投诉的严重后果

## 6、浏览器配置

如果您使用 Internet Expolor 或 Microsoft Edge 浏览器，您无需进行任何操作，如果您使用 Chrome 或 Firefox 浏览器，请查看对应教程

1. [Firefox 浏览器设置教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/7-1-firefox-settings.md)
2. [Chrome 浏览器设置教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/7-2-chrome-settings.md)
