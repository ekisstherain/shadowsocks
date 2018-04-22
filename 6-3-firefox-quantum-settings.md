# Firefox 配合 GFWList 实现自动切换代理 （安装 ProxySwitch Omega 扩展）  
本文适用于 Firefox Quantum （Firefox 57 以上版本）  

这里假设您已经配置好 Shadowsocks 客户端，具体请参考

[Windows 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/2-windows-settings.md)

[macOS 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/3-macos-settings.md)

[Linux 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/6-linux-settings.md)

注：本文并不适合任何手机上的 Firefox 浏览器

## 安装扩展

1、首先前往[插件商店页面](https://addons.mozilla.org/zh-CN/firefox/addon/switchyomega/)安装 ProxySwitch Omega 扩展

## 扩展的配置 

### 1、使用本站提供的已经设置好的备份直接恢复配置（推荐）

通过这个链接下载 switchyomega 的配置文件

Windows 用户[点击这里](https://portal.shadowsocks.to/dl.php?type=d&id=69)下载

macOS 使用客户端为 ShadowsocksX-NG 对应的配置文件：  
[ShadowsocksX-NG 对应的 SwitchyOmega 配置文件](https://portal.shadowsocks.to/dl.php?type=d&id=68)

然后打开 `Proxy SwitchyOmega` 的设置，选择从备份文件恢复，然后选择刚才下载的文件，如图

![](https://ooo.0o0.ooo/2016/06/22/576a3a86d866b.png)

这时点击 `switchyomega` 图标，可以看到有两个模式

```
全局模式
自动切换
```

两个的区別，当你的代理模式选中

1. 全局模式，所有的网址都经过代理。
2. 自动切换，由 GFWlist 更新的被屏蔽网站的网址列表，所有匹配这个列表的网址，都走代理，其它不走代理。

*记得一定要选择 系统代理 / 全局模式/ 自动切换 三者其中之一，选直连不会走代理的*
