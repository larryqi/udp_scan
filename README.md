UDP port scan
===================

###Introduce
这只是我的一个课程作业。

一个非常简单的UDP端口扫描工具，扫描原理基于ICMP端口不可达错误。

默认情况下面，如果某个UDP端口是关闭的，那么向其发送一个UDP数据包，

系统将返回一个ICMP端口不可达的差错。但是这是可以设置的，

很多服务器都设置不发送ICMP端口不可达差错，

再加上UDP协议本身就是不可靠的，因此此程序的局限性非常大。

首先程序置所有端口状态为UNKNOWN，如果受到ICMP数据包设置为CLOSED，

如果收到了UDP的数据包，设置为OPEN。一般情况下就算服务器UDP端口打开，

除非发送了有意义的数据，否则服务器不会返回UDP数据包

###使用

		make				生成test 和 udp_scan
		./test 12345 12346 	打开本地的UDP端口12345和12346
		./dup_scan localhost -s 12344 -e 12349	需要在另一个终端里运行，扫描本地UDP端口从12344到12349。
