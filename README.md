# ubuntu20_cant_connect_to_the_internet
如果你的ubuntu不能联网，且满足如下两个条件：1.电脑是最近购买的，网卡较先进。2.安装ubuntu20后根本没有wifi选项。那么这个笔记可能是有作用的。
# 方法一：有线网连接
## step1
准备网线，正确连接。
## step2
打开终端
## step3
输入 `nmcli con edit type pppoe con-name "My DSL"`

其中"My DSL"是任意设定的网络名称
## step4
输入 `set pppoe.username ISPUsername`

其中ISPUsername是ISP账户名。作者输入了校园网账号。
## step5
输入 `set pppoe.password PASSWORD`

其中PASSWORD是账号的密码。
## step6
输入 `save`,然后输入`yes`
## step7
在网络设置中可以找到名为My DSL的网络连接，点击连接。`
***
# 方法二：无线网连接
## step0 准备工作 
>### 1.确保通过有线网连接到了网络
>### 2.在ubuntu中查看网卡信息，没有出现WLAN。
>### 3.电脑是较先进的。作者的设备信息如下
>>#### 1.网卡：Intel(R) WiFi 6E Ax211 160MHz
>>#### 2.双系统：Windows11 + ubuntu20
>>#### 3.cpu:12th Gen Intel(R) Core(TM) i7-12700H

>### tips 为什么连接不到网络?
>>ubuntu20自带linux内核为**5.13**,过于老旧，建议升级到**5.17**（亲测可行）。
## step1 下载内核
下载网址 https://kernel.ubuntu.com/~kernel-ppa/mainline/
点击后选择对应版本，作者选择5.17。作者cpu架构为amd64，故选择amd64，如下图。**注意一定要下载正确版本，否则无法安装**

![image](https://github.com/OTT123/ubuntu20-can-t-connect-to-the-internet/blob/main/img/pic1.png)
>### tips 下载什么内容？
>>两个headers，一个image，一个modules，共四个。

## step2 安装
在下载好.deb的文件夹打开终端，输入 `sudo dpkg -i *.deb`

## step3 进入系统
安装结束后，重启电脑，在ubuntu高级选项中可以看到自己安装的内核版本的ubuntu，回车进入。可以看到WiFi选项。
![image](https://github.com/OTT123/ubuntu20-can-t-connect-to-the-internet/blob/main/img/pic2.png)


