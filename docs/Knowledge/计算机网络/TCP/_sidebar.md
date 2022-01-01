[返回上一级](./docs/Knowledge/计算机网络/README.md)

TCP篇

[1、TCP 头格式](#_31-tcp-头格式)

[2、为什么需要 TCP 协议？ TCP ⼯作在哪⼀层？](#_32-为什么需要-tcp-协议？-tcp-⼯作在哪⼀层？)



[3、什么是TCP？](#_33-什么是tcp)

[4、什么是 TCP 连接？](#TCP/IP⽹络模型)


[5、如何唯⼀确定⼀个 TCP 连接呢？](#TCP/IP⽹络模型)

[6、有⼀个 IP 的服务器监听了⼀个端⼝，它的 TCP 的最⼤连接数是多少？](#TCP/IP⽹络模型)



[7、UDP 和 TCP 有什么区别呢？分别的应⽤场景是？](#TCP/IP⽹络模型)

[8、为什么 UDP 头部没有「⾸部⻓度」字段，⽽ TCP 头部有「⾸部⻓度」字段呢？](#TCP/IP⽹络模型)


[9、为什么 UDP 头部有「包⻓度」字段，⽽ TCP 头部则没有「包⻓度」字段呢？](#TCP/IP⽹络模型)

[10、 TCP 三次握⼿过程和状态变迁](#TCP/IP⽹络模型)

[11、如何在 Linux 系统中查看 TCP 状态？](#TCP/IP⽹络模型)



为什么是三次握⼿？不是两次、四次？
[12、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

为什么是三次握⼿？不是两次、四次？小结
[13、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

为什么客户端和服务端的初始序列号 ISN 是不相同的？
[14、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

初始序列号 ISN 是如何随机产⽣的？
[15、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

既然 IP 层会分⽚，为什么 TCP 层还需要 MSS 呢？
[16、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

什么是 SYN 攻击？如何避免 SYN 攻击？
[17、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TCP 四次挥⼿过程和状态变迁
[18、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

为什么挥⼿需要四次？
[19、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


为什么 TIME_WAIT 等待的时间是 2MSL？

[20、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

为什么需要 TIME_WAIT 状态？
[21、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TIME_WAIT 过多有什么危害？
[22、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如何优化 TIME_WAIT？
[23、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如果已经建⽴了连接，但是客户端突然出现故障了怎么办？
[24、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

针对TCP应该如何Socket编程？
[25、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

listen 时候参数 backlog 的意义？
[26、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


 accept 发⽣在三次握⼿的哪⼀步？
[27、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

客户端调⽤ close 了，连接是断开的流程是什么？
[28、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


为了⽅便调试服务器程序，⼀般会在服务端设置 SO_REUSEADDR 选项，这样服务器程序在启后，可以⽴刻使⽤。这⾥设置SO_REUSEADDR 是不是就等价于对这个 socket 设置了内核中的net.ipv4.tcp_tw_reuse=1 这个选项？”

[29、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


如果客户端第四次挥⼿ack丢失，服务端超时重发的fin报⽂也丢失，客户端timewait时间超过了2msl，这个时候会发⽣什么？认为连接已经关闭吗？”
[30、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


⽂章在解释IP分⽚和TCP MSS分⽚时说，如果⽤IP分⽚会有两个问题：（1）IP按MTU分⽚，如果某⼀⽚丢失则需要所有分⽚都重传；（2）IP没有重传机制，所以需要等TCP发送⽅超时才能重传；问题⼀：MSS跟IP的MTU分⽚相⽐，只是多了⼀步协商MSS值的过程，⽽IP的MTU可以看作是默认协商好就是1500字节，所以为什么协商后的MSS可以做到丢失后只发丢失的这⼀⽚来提⾼效率，⽽默认协商好1500字节的IP分⽚就需要所有⽚都重传呢？问题⼆：TCP MSS分⽚如果丢失了⼀⽚，是不是也需要发送⽅等待超时再重传？如果不是，MSS的协商如何能在超时前就直到丢了分⽚从⽽提⾼效率的呢？
[31、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


如果是服务提供⽅发起的 close ，然后引起过多的 time_wait 状态的 tcp 链接，time_wait 会影响服务端的端⼝吗？
[32、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


 重传机制
[33、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

滑动窗⼝
[34、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


窗⼝⼤⼩由哪⼀⽅决定？
[35、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


发送⽅的滑动窗⼝
[36、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)




程序是如何表示发送⽅的四个部分的呢？
[37、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

接收⽅的滑动窗⼝
[38、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

接收窗⼝和发送窗⼝的⼤⼩是相等的吗？
[39、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

流量控制
[40、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

 窗⼝关闭潜在的危险
[41、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

 TCP 是如何解决窗⼝关闭时，潜在的死锁现象呢？
[42、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

怎么让接收⽅不通告⼩窗⼝呢？
[43、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

怎么让发送⽅避免发送⼩数据呢？
[44、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

为什么要有拥塞控制呀，不是有流量控制了吗？
[45、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

什么是拥塞窗⼝？和发送窗⼝有什么关系呢？
[46、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

那么怎么知道当前⽹络是否出现了拥塞呢？
[47、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

拥塞控制有哪些控制算法？
[48、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)




TCP 实战抓包分析
[49、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

tcpdump 和 Wireshark 有什么区别？
[50、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

 tcpdump 在 Linux 下如何抓包？
[51、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

Wireshark ⼯具如何分析数据包？
[52、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


解密 TCP 三次握⼿和四次挥⼿
[53、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


为什么三次握⼿连接过程的 Seq 是 0 ？

[54、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


为什么抓到的 TCP 挥⼿是三次，⽽不是书上说的四次？
[55、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

 TCP 三次握⼿异常情况实战分析
[56、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


咦？客户端设置了防⽕墙，屏蔽了服务端的⽹络包，为什么 tcpdump 还能抓到服务端的⽹络包？
[57、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

tcp_syn_retries 是限制 SYN 重传次数，那第⼆次握⼿ SYN、ACK 限制最⼤重传次数是多少？

[58、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


TCP 第⼀次握⼿的 SYN 包超时重传最⼤次数是由 tcp_syn_retries 指定，TCP 第⼆次握⼿的 SYN、ACK 包超时重传最⼤次数是由 tcp_synack_retries 指定，那 TCP 建⽴连接后的数据包最⼤超时重传次数是由什么参数指定呢？
[59、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


那如果客户端不发送数据，什么时候才会断开处于 ESTABLISHED 状态的连接？
[60、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)




TCP 快速建⽴连接
[61、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

在 Linux 上如何打开 Fast Open 功能？
[62、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TCP Fast Open 抓包分析
[63、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TCP 重复确认和快速重传
[64、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TCP 流量控制
[65、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

在 Wireshark 看到的 Windows size 也就是 " win = "，这个值表示发送窗⼝吗？
[66、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如何在包⾥看出发送窗⼝的⼤⼩？
[67、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

发送窗⼝和 MSS 有什么关系？
[68、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

发送⽅在⼀个窗⼝发出 n 个包，是不是需要 n 个 ACK 确认报⽂？
[69、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

TCP 延迟确认与 Nagle 算法

[70、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)
Nagle 算法是如何避免⼤量 TCP ⼩数据报⽂的传输？

[71、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

那延迟确认⼜是什么？
[72、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


延迟确认 和 Nagle 算法混合使⽤时，会产⽣新的问题
[73、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


tcp_retries1 参数，是什么场景下⽣效？tcp_retries2是不是只受限于规定的次数，还是受限于次数和时间限制的最⼩值？”
[74、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

tcp_orphan_retries也是控制tcp连接的关闭。这个跟tcp_retries1 tcp_retries2有什么区别吗？
[75、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

请问，为什么连续两个报⽂的seq会是⼀样的呢，⽐如三次握⼿之后的那个报⽂？还是说，序号相同的是同⼀个报⽂，只是拆开显示了？
[76、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


TCP 半连接队列和全连接队列
[77、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

在 TCP 三次握⼿的时候，Linux 内核会维护两个队列，分别是：
[78、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


实战 - TCP 全连接队列溢出之如何知道应⽤程序的 TCP 全连接队列⼤⼩？
[79、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如何模拟 TCP 全连接队列溢出的场景？
[80、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)


Linux 有个参数可以指定当 TCP 全连接队列满了会使⽤什么策略来回应客户端。
[81、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如何增⼤ TCP 全连接队列呢？
[82、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

增⼤ TCP 全连接队列后，继续压测
[83、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

实战 - TCP 半连接队列溢出之如何查看 TCP 半连接队列⻓度？
[84、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

如何模拟 TCP 半连接队列溢出场景？
[85、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

⼤部分⼈都说 tcp_max_syn_backlog 是指定半连接队列的⼤⼩，是真的吗？
[86、TCP/IP ⽹络模型？](#TCP/IP⽹络模型)

半连接队列最⼤值 max_qlen_log 就表示服务端处于 SYN_REVC 状态的最⼤个数吗？


每个 Linux 内核版本「理论」半连接最⼤值计算⽅式会不同。


如果 SYN 半连接队列已满，只能丢弃连接吗？



如何防御 SYN 攻击？



读者问：“syncookies 启⽤后就不需要半链接了？那请求的数据会存在哪⾥？”



TCP 内核参数


TCP 三次握⼿的性能提升


如何查看由于 SYN 半连接队列已满，⽽被丢弃连接的情况？



如何调整 SYN 半连接队列⼤⼩？



如果 SYN 半连接队列已满，只能丢弃连接吗？



SYN_RCV 状态的优化



accept 队列已满，只能丢弃连接吗？


如何调整 accept 队列的⻓度呢？


如何查看服务端进程 accept 队列的⻓度？



如何查看由于 accept 连接队列已满，⽽被丢弃的连接？


如何绕过三次握⼿？


TCP Fast Open 功能的⼯作⽅式。



Linux 下怎么打开 TCP Fast Open 功能呢？

优化策略总结

TCP 四次挥⼿的性能提升

 主动⽅的优化

 被动⽅的优化

小结 TCP 四次挥⼿的优化


TCP 传输数据的性能提升


小结TCP优化数据传输的方式

如果 accept 队列满了，那么 server 扔掉 client 发过来的 ack”，也就是说该TCP连接还是位于半连接队列中，没有丢弃吗？”

