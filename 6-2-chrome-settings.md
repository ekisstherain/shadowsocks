# Chrome + Proxy SwitchyOmega 设置

这里假设您已经配置好 Shadowsocks 客户端，具体请参考

[Windows 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/2-windows-settings.md)

[macOS 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/3-macos-settings.md)

[Linux 下安装配置 Shadowsocks 使用教程](https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/6-linux-settings.md)

注：本文并不适合任何手机上的 Firefox 浏览器  

## 1、安装扩展

您可以通过chrome商店安装 [Proxy SwitchyOmega](https://chrome.google.com/webstore/detail/padekgcemlokbadohgkifijomclgjgif) 扩展

如果无法访问，您也可以直接在 [Github](https://github.com/FelisCatus/SwitchyOmega/releases) 下载 .crx 文件并拖入 `chrome://extensions/` （请使用 Chrome 浏览器复制粘贴输入地址栏并回车访问）

本扩展同样适用于 Firefox 57 (Firefox Quantum) 以上版本: 安装链接 [Proxy SwitchyOmega](https://addons.mozilla.org/zh-CN/firefox/addon/switchyomega/)

## 2、扩展的配置(以下方法 2 选 1 即可)

### 1、使用本站提供的已经设置好的备份直接恢复配置（推荐）

通过这个链接下载 switchyomega 的配置文件

Windows 用户[点击这里](https://portal.shadowsocks.to/dl.php?type=d&id=39)下载

macOS 用户按客户端不同分有两种：

1. [shadowsocksx对应的switchyomega配置文件](https://portal.shadowsocks.to/dl.php?type=d&id=55)
2. [shadowsocksx-ng对应的switchyomega配置文件](https://portal.shadowsocks.to/dl.php?type=d&id=54)

然后打开 `Proxy SwitchyOmega` 的设置，选择从备份文件恢复，然后选择刚才下载的文件，如图

![](https://ooo.0o0.ooo/2016/06/22/576a3a86d866b.png)

这时点击 `switchyomega` 图标，可以看到有三个模式

```
ss
ss-白名单
ss-黑名单
```

三个的区別，当你的代理模式选中

1. ss，所有的网址都经过代理。
2. ss-白名单，内置一个列表，所有匹配这个列表的网址，都不走代理，其它走代理
3. ss-黑名单，内置一个列表，所有匹配这个列表的网址，走代理，其它不走代理
注： 也可以选中系统代理，即使用上面所提到的系统代理

*记得一定要选择 系统代理 / ss / ss-白名单 / ss-黑名单 四者其中之一，选直连不会走代理的*

（如果不准备使用本站提供的配置文件并且希望配合 GFWList 规则实现自动代理，请看下面内容）

**（如果使用了本站提供的配置文件，请忽视下面的内容）**

### 2、设置配合 GFWList 实现自动切换的模式

按照下图所示

1. 单击新建情景模式，在弹出的窗口中选中自动切换，并且将名称填写为自动切换或其他名称
2. 在新的页面，首先单击添加在线规则
![](https://ooo.0o0.ooo/2016/06/22/576aaba960469.png)
3. 将规则列表规则对应的 ③ 的位置地方选为 Shadowsocks 对应的规则，如果之前是导入本站的备份的话，请选中 ss 即可。
4. 将规则列表格式选中 AutoProxy
5. 在规则列表网址中填入
`https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt`

![](https://ooo.0o0.ooo/2016/06/22/576aa998042f0.png)

之后可以可以通过选中该模式实现自动代理，如果特殊需要的域名也可以手动通过添加条件指定代理
