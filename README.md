据说 V2Ray 是个强大的工具，支持各种协议各种伪装，就是上手较难，现在看其实也就是配置比较难懂而已。过了这么久也有好多客户端配置起来相对简单了，也不用去怎么理解协议了。

搬瓦工一月份刚买的服务器 IP 就被毙了，白白浪费了20美金， 不能再上 SS 或者 SSR 了。那就搞搞 V2Ray 吧。

这篇文章写了几个月没发，现在发现搬瓦工的 IP 居然通了，意外之喜。

Github 项目地址：https://github.com/pcb900817/v2ray
1. 服务器端的安装，配置。
系统要求

1.  Debian 9（推荐）
2.  Ubuntu 14
3.  Ubuntu 16
4.  CentOS 7
其他Linux版本不建议  
# 购买一台vps
## 狗云香港
|  CPU   | 带宽  |  流量   | 价格  | 购买链接  |
|  ----  | ----  | ----  | ----  | ----  |
| 1 vCPU  | 50 Mbps | 500 GB/月 | ￥39.00/月 | <a href="https://www.dogyun.com/?ref=jv98open" target="_blank">购买</a> |
| 1 vCPU  | 50 Mbps | 800 GB/月 | ￥49.00/月 | <a href="https://www.dogyun.com/?ref=jv98open" target="_blank">购买</a> |   

  
  <img src="https://download.shluqu.cn/wp-content/uploads/2021/05/QQ%E6%88%AA%E5%9B%BE20210510124515-1024x553.png" width = "80%" height = "80%" alt="图片名称" align=center />

## 搬瓦工
想要搭建 V2Ray， 拥有一个 VPS 是必需的。
我们推荐使用：<a href="https://bwh88.net/aff.php?aff=68113&pid=58" target="_blank">搬瓦工（Bandwagon Host）</a> VPS 来搭建 V2Ray，搬瓦工是一个对中国用户极度友好的 VPS 商家，有香港，CN2 GIA 等线路，支持支付宝付款，当然也是支持退款的！

|  CPU   | 带宽  |  流量   | 价格  | 购买链接  |
|  ----  | ----  | ----  | ----  | ----  |
| 2 vCPU  | 1 G | 1 TB/月 | $49.99 / 年 | <a href="https://bwh88.net/aff.php?aff=68113&pid=58" target="_blank">购买</a> |  

## 搬瓦工这款是最火热的 其他版本的不划算



官方安装脚本自行搜索(较麻烦，所以我直接删除了)

VIM 快捷键使用：

输入i 进入编辑模式，修改完毕，Esc键退出编辑模式，输入:w保存文件，输入:q退出vim编辑。

 #  推荐的一键安装脚本：
root 账号
切换root权限:
```
sudo -i
```
一键安装命令：
```
bash <(curl -s -L https://git.io/v2ray.sh)
```
# 安装教程

如果提示 curl: command not found ，那是因为你的 VPS 没装 Curl  
ubuntu/debian 系统安装 Curl 方法: apt-get update -y && apt-get install curl -y  
centos 系统安装 Curl 方法: yum update -y && yum install curl -y  
安装好 curl 之后就能安装脚本了


没啥需求就用 TCP
追求更加安全就用 WS + TLS
ISP 多作怪用动态端口
VPS 网络不好就用 mKCP
基本上按照提示一步步选择，回车就可以搞定了。

配置及管理
V2Ray 配置文件路径：/etc/v2ray/config.json

手动配置打开这个文件就好了。至于输入输出怎么填我就不写了，官方文档能看懂的就自己填，看不懂的就用一键脚本了。

###快速管理命令：
#### v2ray info | 查看 V2Ray 配置信息

#### v2ray config  | 修改 V2Ray 配置

#### v2ray link  | 生成 V2Ray 配置文件链接

#### v2ray infolink  | 生成 V2Ray 配置信息链接

#### v2ray qr  | 生成 V2Ray 配置二维码链接

#### v2ray ss  | 修改 Shadowsocks 配置

#### v2ray ssinfo  | 查看 Shadowsocks 配置信息

#### v2ray ssqr  | 生成 Shadowsocks 配置二维码链接

#### v2ray status  | 查看 V2Ray 运行状态

#### v2ray start  | 启动 V2Ray

#### v2ray stop  | 停止 V2Ray

#### v2ray restart  | 重启 V2Ray

#### v2ray log  | 查看 V2Ray 运行日志

#### v2ray update  | 更新 V2Ray

#### v2ray update.sh  | 更新 V2Ray 管理脚本

#### v2ray uninstall  | 卸载 V2Ray


 

2. 客户端配置
V2RayW Win
下载：https://github.com/Cenmrev/V2RayW

V2RayN Win
下载：https://github.com/2dust/v2rayN

V2RayX MAC
下载：https://github.com/Cenmrev/V2RayX

考虑到部分电脑软件只支持http协议，本地监测的端口有socks和http这俩。

127.0.1.1+1081是socks。
127.0.2.1+1082是http。
使用方法：

手机配置更简单，我用的 v2rayNG 直接扫描生成的二维码就好了。

一般协议的安装配置到此就结束了，可以直接去使用了。


安装时传输协议选择 WebSocket (即选择 3 )，V2Ray 端口选择 80，其他就默认。等待安装完成之后生成二维码或者配置参数。

输入 v2ray status 看看 V2Ray 有没有在运行，如果没有，使用 netstat -lp 看看是什么程序占用了 80 / http ，解决占用程序，然后使用 v2ray start 启动 V2Ray。

