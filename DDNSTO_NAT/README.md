# DDNSTO_NAT
# 使用[DDNSTO](https://www.ddnsto.com/)进行内网穿透


## 教程包括基本的路由器管理页面穿透和进阶的Download_Master页面穿透2部分（本教程使用RT-AX86U 梅林改版固件进行说明）

## 一、系统要求和前期准备
- 支持DDNSTO插件的路由器，可以刷固件之后进行安装


## 二、插件安装与配置
## 1.在路由器的Koolshare 软件中心安装 DDNSTO
![](https://github.com/sheldonl3/Playing-strategy/blob/master/DDNSTO_NAT/ddnsto_install.png)
## 2.登录官网-[控制台](https://www.ddnsto.com/app/#/devices)拿到token
![](https://github.com/sheldonl3/Playing-strategy/blob/master/DDNSTO_NAT/token.png)
## 3.路由器安装好 DDNSTO 之后在软件中填入 Token
![](https://github.com/sheldonl3/Playing-strategy/blob/master/DDNSTO_NAT/tian%20token.png)


## 三、路由器管理页面穿透
### 1.ddnsto官网用户中心出现设备后，点击添加域名映射"+"
### 2.添加域名前缀，根据自己的命名原则
### 3.在目标主机一栏填入路由器LAN口IP地址，如http://192.168.50.1:80 ( 端口是80，可以省略端口如：http://192.168.50.1 ）填写完毕后点击"添加"。
### 4.成功添加后请稍等1分钟左右，通过访问绑定的域名即可访问路由器，首次访问可能需要微信登录验证。


## 四、Download_Master页面穿透
### 1.打开路由器的Download_Master，进入设置-一般设置，查看Download_Master端口
![](https://github.com/sheldonl3/Playing-strategy/blob/master/DDNSTO_NAT/dm.png)
### 2.在官网控制台设置新域名，绑定ip地址为http://路由器IP:端口号
### 3.如果使用https穿透后Download_Master自动跳转会出现问题，所以需要自己补齐链接，假如路由器的IP是192.168.50.11，并且绑定了域名https://download.kooldns.cn/ ,但这个链接是不能访问的！！！需要在链接后加上 /Main_Login.asp 也就是说完整链接为：https://download..ddnsto.com/Main_Login.asp
### 用HTTP协议访问可以忽略上面的这个问题：http://download.kooldns.cn:5000/ 这个就可以直接访问了，不需要手动补齐
### 4.成功添加后请稍等1分钟左右，通过访问绑定的域名即可访问。

#### 本教程参考易有云文档[易有云](https://doc.linkease.com/zh/guide/ddnsto/#%E5%AE%89%E8%A3%85%E4%B8%89%E6%AD%A5%E8%B5%B0)
