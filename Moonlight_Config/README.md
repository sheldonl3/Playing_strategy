# 使用Moonlight进行PC串流教程

使用[Moonlight](https://github.com/moonlight-stream)与Nvidia Geforce Experience进行PC（游戏）串流，分为本地串流和远程串流2种方式。

## 一、系统要求和前期准备
- 串流PC:使用N卡，GTX 600以上型号，并且安装Nvidia Geforce Experience
- 可以对家庭路由器进行配置
- 拥有接受串流的移动设备
- 远程串流需要公网ip

## 二、本地串流
本地串流比较容易，就是串流PC和接受串流的移动设备在同一个局域网中，只要安装好软件既可以使用

### 1）串流PC配置
在串流PC中打开Geforce Experience，在设置里面的"SHIELD"中打开“GAMESTREAM”选项
![](https://github.com/sheldonl3/Playing-strategy/blob/master/Moonlight_Config/gfe.png)
GFE默认会添加支持串流的游戏，并且可以添加任何程序

### 2）移动端配置
安装moonlight客户端，默认搜索局域网内开启GAMESTREAM功能的PC，之后进行连接配对即可使用


## 三、远程串流
远程串流是使用外部网络连接家庭内网的游戏主机进行串流，需要解决内网的访问问题
![](https://github.com/sheldonl3/Playing-strategy/blob/master/%E7%BD%91%E7%BB%9C%E6%8B%93%E6%89%91.png)
可以使用IPV4或者IPV6进行串流，但是IPV6的访问需要路由器的支持，并且能够配置IPV6防火墙，由于条件限制本文使用IPV4。
远程串流需要公网ip，没有的同学可以向客服索要。
因为用户从外网访问，因此要进行nat转发，需要通过对调制解调器和路由器进行配置。

### 1）调制解调器
配置最简单的方式是路由器使用桥接模式，关闭防火墙，但是这样对原本的网络功能有较大的影响。
这里保留光猫和路由器的原始链接方式，通过2层nat实现连通。
首先为了保证路由器lan地址不变，根据路由器使用的mac地址配置静态ip地址
![](https://github.com/sheldonl3/Playing-strategy/blob/master/%E9%9D%99%E6%80%81.png)

在moonlight的[Setup Guide](https://github.com/moonlight-stream/moonlight-docs/wiki/Setup-Guide)中可以找到服务使用的端口
- TCP 47984, 47989, 48010
- UDP 47998, 47999, 48000, 48010

在nat中对静态lan地址配置端口转发
![](https://github.com/sheldonl3/Playing-strategy/blob/master/nat2.png)

### 2)路由器
首先主机绑定静态IP
![](https://github.com/sheldonl3/Playing-strategy/blob/master/%E9%9D%99%E6%80%81ip.png)

对主机同样的端口配置nat，这样串流流量通路顺利打通
![](https://github.com/sheldonl3/Playing-strategy/blob/master/nat.png)

使用[端口检测](https://www.canyouseeme.org/)工具可以检测是否配置成功（只需检测47984 47989，其他端口使用时才开放）


### 3）PC配置和移动端
和本地串流方式相同，无序做多余配置，GFE默认开启所有服务。
最后使用连接外网的移动端，没有问题的话可以正常连接主机。


## 四、进阶功能
### 1）远程开机

## 五、问题解决

内容参考moonlight文档和[b站专栏](https://www.bilibili.com/read/cv6333264?from=search)