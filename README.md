# ubuntu20-can-t-connect-to-the-internet
如果你的ubuntu不能联网，且满足如下两个条件：1.电脑是最近购买的，网卡较先进。2.安装ubuntu20后根本没有wifi选项。那么这个笔记可能是有作用的。。
# 方法一：有线网连接
## step1
准备网线，正确连接。
## step2
打开终端
## step3
输入 `nmcli con edit type pppoe con-name "My DSL"`

其中"My DSL"是任意设定的网络名称
## step4
