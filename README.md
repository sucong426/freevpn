# 新手搭建vpn科学上网教程

## 自己搭建VPN科学上网

或许你获取到的很多资料和资源并不是一手信息，还有很多是被屏蔽了而自己无法访问得到，市面上有很多厂家提供了VPN服务，你可以购买后直接使用，但是你会遇到很多问题，例如不安全，很多人同时使用被限制，流量被限制，平台说关停就关停，而如果自己搭建一个完全属于自己的VPN，那么自己想要怎么使用都可以，访问速度很快，而且通过自己的代理，走自己的云服务器，加密上网很安全。

事实上，对于新手来说，想要自己搭建 VPN，会觉得很麻烦，无从下手，其实搭建一个属于自己的 VPN 并不难，因为现在已经有很多开源的脚本，往往只需要在自己的境外云服务器上执行几行命令就可以实现了。

## 拥有自己的境外云服务器

境外云服务器推荐使用 [vultr](https://www.vultr.com/?ref=8872889)，这是一家专门做服务器的厂商，已经做了很多年了，服务器稳定可靠，你可以理解为国内的阿里云服务器。

值得说的一点是， [vultr](https://www.vultr.com/?ref=8872889) 给新用户的福利相当给力，充值 10 美元就可以获取 100 美元，你可以点击 [vultr 专属赠送新用户 100 美元](https://www.vultr.com/?ref=8872889) 进去抢先注册，可以使用支付宝直接付款，不用国外的信用卡。

右上角有注册按钮，你也可以切换成中文界面：

<img width="1446" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png">

![](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)

接着使用邮箱和密码就可以注册了。

![](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)

进去之后你可以看到这个页面，说明你已经通过 [vultr 专属优惠链接](https://www.vultr.com/?ref=8872889) 获得了 100 美元赠送的资格：

![](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)

现在你只要选择支付宝充值 10 美元以上，就可以获得额外赠送的 100 美元。

![](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)

接下来就可以在这个平台选购云服务器了。

点击页面左边菜单栏的 「Products」进入服务器选购页面。

### Choose Server 选择服务器

选择 Cloud Compute 即可：

![](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)

### Server Location

服务器的位置，可以选择美国地区，比如纽约：

![](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)

### Server Type

服务器类型，CentOS 8 x64 系统：

<img width="1297" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020720-198b8280-b98e-11eb-9df3-19bf5a187a1e.png">

### Server Size

内存，个人使用10G完全够用，这里选择3.5美元一个月，性价比高，注意不要选择IPv6 ONLY的，要不然无法搭建使用。

<img width="1240" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020895-4a6bb780-b98e-11eb-9ac8-3cdd4f4397de.png">

选择完了之后，下面的其它东西都不需要填，直接点击右下角 Deploy Now 就可以了：

![](https://user-images.githubusercontent.com/84239400/119020981-68391c80-b98e-11eb-9f16-00c75de88eeb.png)

这时候你就拥有了自己的一台云服务器了：

<img width="1261" alt="VPN搭建教程" src="https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png">


点击 Cloud Instance ，可以看到你服务器的 IP 地址和密码：

<img width="1308" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png">

## 搭建 vpn 前的了解

### 什么是V2Ray

Project V 提供了单一的内核和多种界面操作方式。内核（V2Ray）用于实际的网络交互、路由等针对网络数据的处理，而外围的用户界面程序提供了方便直接的操作流程，简单来说，V2Ray就是一个代理软件，可以用来科学上网学习国外先进科学技术。

### V2Ray与Shadowsocks区别

V2Ray是在Shadowsocks的作者被请喝茶之后出现的一个开源项目，目的就是为了更好的科学上网。相比于ss，V2Ray的定位是一个平台，任何开发者都可以在这个平台上利用V2Ray开发出一个新的代理软件，简单来说，ss的定位比较简单，功能也比较单一，而V2Ray的功能非常强大，相对的，V2Ray的配置就会复杂很多，喜欢鼓捣的同学可以试试。

### V2Ray的优势

        - 更完善的协议: V2Ray 使用了新的自行研发的 VMess 协议，改正了 Shadowsocks 一些已有的缺点，更难被墙检测到（不保证可靠性）
        - 更强大的性能: 网络性能更好，具体数据可以看 V2Ray 官方博客
        - 更丰富的功能:

### 以下是部分 V2Ray 的功能

        - mKCP: KCP 协议在 V2Ray 上的实现，不必另行安装 kcptun
        - 动态端口：动态改变通信的端口，对抗对长时间大流量端口的限速封锁
        - 路由功能：可以随意设定指定数据包的流向，去广告、反跟踪都可以
        - 传出代理：看名字可能不太好理解，其实差不多可以称之为多重代理。类似于 Tor 的代理
        - 数据包伪装：类似于 Shadowsocks-rss 的混淆，另外对于 mKCP 的数据包也可伪装，伪装常见流量，令识别更困难
        - WebSocket 协议：可以 PaaS 平台搭建V2Ray，通过 WebSocket 代理。也可以通过它使用 CDN 中转，抗封锁效果更好
        - Mux:多路复用，进一步提高科学上网的并发性能



## 连接到你的服务器

### windows 系统连接到 vultr 服务器

windows 可以下载[PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)工具。

打开之后选择 session，将你在 vultr 网上得到的服务器 ip 复制过来，输入到这里：

![](https://user-images.githubusercontent.com/84239400/119023900-037fc100-b992-11eb-85ea-525a61a69657.png)

Port 默认 22，Connection Type 选择 SSH，接着点击 Open，连接进去之后输入你云服务器的密码。

### Linux 和 MacOS 连接到 vultr 服务器

Linux 和 MacOS 可以打开终端，使用如下命令连接：

```
ssh root@xx.xx.xxx.xx
```

`xx.xx.xxx.xx`就是你的服务器上的 IP 地址。

连接进去之后输入 yes 后按回车，接着输入你云服务器的密码，即可使用云服务器。

<img width="772" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024049-32963280-b992-11eb-8c05-db6df1f7fbfa.png">



## 快速搭建 VPN


### 安装必要的库：

```
sudo yum -y install wget gcc gcc-c++ autoconf automake make
```

### 安装 VPN 脚本 ss.sh:

```
wget –no-check-certificate -O ss.sh https://raw.githubusercontent.com/sucong426/VPN/main/ss.sh
```

### 执行脚本

```
sh ss.sh
```

<img width="791" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024123-45a90280-b992-11eb-9ea5-514542f71594.png">


设置你的 VPN 密码。

接着输入你 VPN 的端口，可以直接回车。

接着输入加密方式，你可以选择 7:

<img width="574" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024193-59546900-b992-11eb-8d71-81681e582e38.png">

设置好了之后，按一下回车就可以开始安装，稍等一会，出现以下信息说明安装成功：

<img width="645" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024277-6bcea280-b992-11eb-90a9-7fa45cbdc97d.png">


这是属于你自己 VPN 的 IP 地址，端口号，密码，加密方式。把它们复制下来，然后就可以使用客户端连接这个代理从而访问Google了。

复制号信息之后，服务器连接可以关掉，它会一直运行。



## 开始使用 VPN

### PC 端使用 VPN

点击下载[shadowsocks](https://github.com/shadowsocks/shadowsocks-windows/releases/download/4.4.0.0/Shadowsocks-4.4.0.185.zip)，可参考：[Shadowsocks Windows客户端快速使用指南](https://www.howru.cc/articles/414.html)

 ### 手机使用 VPN

去应用市场下载 shadowsocks，配置好你自己云服务器得到的 IP 地址，端口号，密码，加密方式，开启代理即可访问。

## 访问 Google

速度可以：

![](https://user-images.githubusercontent.com/84239400/119024332-7b4deb80-b992-11eb-8616-d63fd5aca694.png)


## 赞赏

点赞：如果你喜欢本项目，如果您是github用户，请给我们“点个赞”，请点GitHub右上角的star。同时您还可以通过GitHub的Fork功能（点右上角Fork）备份和二次开发本项目。

收藏：也推荐您可以将当前页面网址放入您的浏览器收藏夹、书签栏等

收藏方法：电脑访问可按Ctrl+D 键，手机访问请按手机收藏方法收藏
