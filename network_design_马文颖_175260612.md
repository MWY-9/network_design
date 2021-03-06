#       南京林业大学
# 网络工程和组网课程设计报告

  + **学院：信息技术科学学院**
  + **专业：计算机科学与技术**
  + **姓名：马文颖**
  + **班级：1752603**
  + **学号：175260612**
  
  ### 摘要：
&emsp;&emsp;根据课程设计任务和需求分析，在南京林业大学现有配置的情况上进行了这次学生公寓组网方案的设计。设计报告中提出了系统总体设计、网络拓扑结构设计、物理设计和IP地址分配。网络组网拓扑考虑到网络的安全性、实用性、开放性和可靠性等设计原则进行仔细的分析和设计,最后提出可行性的方案； IP地址分配需要考虑多方面因素，包括后续可拓展性、地址的利用率等方面，设计中详细地提出了符合我校现有条件的IP地址分配方案。最后对此次课程设计进行了分析与总结。
    
### 一、设计任务和目的
1. 题目：学生公寓组网方案设计
2. 内容：分析所在公寓的上网需求，进行学生公寓组网设计，设计时要考虑到先进性、可靠性、开放性、经济性、安全性和可管理性，并遵循标准化、实用性、安全性、开放性、可维护性、高性能等原则。
3. 目的:
 <br/>1)加深对计算机网络的工作原理的理解，并提高网络应用能力
 <br/>2)能够初步使用git、github做文档和版本管理
 <br/>3)能够使用Markdown做基本的文档编辑
4. 任务:
<br/>1)完成学校公寓上网的需求分析和可行性分析
<br/>包括你所在宿舍的公寓，共选取4到6幢公寓进行组网设计
<br/>2)完成系统总体设计、网络拓扑结构设计、物理设计（设备选型）和IP地址分配
<br/>3)利用Markdown撰写课程设计报告，并用github做版本管理
<br/>Markdown的撰写可以利用github网站的编辑器，也可以利用RStudio等工具来编辑
<br/>文档中注明文档所在github网站上的地址，所创建的项目应该是公开的，便于访问和检查
### 二、需求分析
1. 核心交换设备要求具有强大的处理能力和良好的安全性、可靠性、可扩展性；要有未来展望性。
2. 接入层网络设备需要支持基于MAC地址802.1x功能和基于端口802.1x功能，以此保证账号的唯一性。同时，支持远程Telnet管理及远程开关交换机端口功能；此外还要求适应大量用户并发认证及复杂的工作环境等。
3. 要求能够实现对用户名、IP地址、MAC地址、交换机端口、交换机IP的同时绑定，以此杜绝非法用户恶意盗用合法用户信息，确保计费与流量控制工作。
4. 解决用户私自架设代理服务器的现象。
5. 支持标准Radius认证计费，可连接多种接入设备。一方面要求设备支持802.1x认证方式；另一方面又要求系统支持基于时长、流量以及包月的计费模式，从而为网络管理提供完善、灵活、可定制的计费策略；同时还需要保证20000个以上用户并行时网络运营的稳定和管理简便。
### 三、可行性分析
<br/>&emsp;&emsp;学生公寓网比较特殊，除了一般网络所必需的可靠性、稳定性和安全性等条件外，在进行学生公寓网建设规划时，还应该考虑所有信息点的可控性、高性能以及关键业务的QoS保证等。另外还要考虑到如何预留扩展空间，以满足新应用的需求以及信息量增长和变化需要，这也是学生公寓组网建设过程中需要重点考虑的一方面。
<br/>&emsp;&emsp;在充分考虑学生公寓网的多应用、易管理的同时，本方案同时还遵循下列原则:
1. 高性能
<br/>构建宿舍网的组网技术必须是高带宽的组网技术。主干交换设备必须支持线速交换，以保证无阻塞的数据交换；另外，从网络结构设计上，需要考虑到一些高流量多媒体应用的分布式部署，以降低跨主干网络的流量，提高网络的性能。
2. QoS服务质量保证
<br/>宿舍网中有各种各样的应用业务数据流，当网络流量处于高峰期时，比如学生网上选课，必定会影响关键业务数据流的响应时间。因此，高性能的网络也还是需要QoS服务质量保证的。
3. 信息点可控性
<br/>宿舍网的信息点分布很广，学生宿舍网用户的流动性大，比较难管理，为了保证网络资料的有效利用，对信息点的可控性要求是必须的。除了对访问带宽限制，还必须接入认证、授权和计费。为了不影响网络性能，应该在接入层设备分布式实现信息点的控制。
4. 先进性
 <br/>所选的设备必须具有很好的扩展性，当网络规模或带宽需要扩展时，能够以最小的代价满足新的需求。
5. 可靠稳定性
 <br/>可靠稳定的网络平台是应用业务系统得以实施和推广的基石。网络平台的设计必须从设备、网络拓扑结构、网络技术等几个方面保证网络的可靠稳定性。
6. 安全性
 <br/>除了要保障网络平台的安全性，还需要在一定程度上保障应用业务系统和其它网络资源的安全。网络平台应该从几个方面保证网络安全:
 <br/>1)设备本身的访问安全；
 <br/>2)内部网之间资源访问安全；
 <br/>3)路由系统的安全；
 <br/>4)互联网访问安全。
### 四、网络拓扑设计方案
1. 公寓概貌
<br/>(1)抽出大学的6幢学生公寓进行组网设计，分别编号为1到6号楼。其中6栋楼均为六层，每层有30个房间。总共有1080个房间。
<br/>(2)学生宿舍每个房间设置1个信息点。
2. 网络拓扑初步规划
<br/>(1)针对用户需求，整个网络采用分布式三层交换构架，具有超高的带宽和良好的可扩展、可管理性。
<br/>(2)每幢学生公寓设置一台核心交换机(即第二层交换机)，每楼层设置两台交换机(即第三层交换机)，网络主干线从网络管理中心拉出，分别到达每个学生公寓的核心交换机，每楼层的交换机直接和本楼的核心交换机相连，满足基本的建网需求。
<br/>(3)网络规划的总体拓扑图如下:
<br/>![](http://m.qpic.cn/psc?/V14aMFsz1pP4hB/wZu0*zqyEz4NDRuTFUPfB8mU*0iUwPrupgOtoSLOvTaszQ7PH67zENtViiWep*k*1bmu5b9SFyLPT.mjDczuRw!!/b&bo=LgNjAwAAAAARB30!&rf=viewer_4)
3. 网络拓扑方案
<br/>(1) 由网络中心到各个宿舍楼之间的布线情况如下:
<br/>&emsp;&emsp;假设南京林业大学有6幢学生公寓楼，所有校内用户要连接外部Internet都需经由网络管理中心，这样由网络管理中心布线到学生公寓就需要至少七个端口的交换机进行连接。我们这个选用两个16口的自适应交换机实现从网络管理中心到各幢学生公寓的网络连接。这样就可以满足提供6幢楼的连接，每台交换机还余下9口可用于以后的拓展。
<br/>&emsp;&emsp;其拓扑结构如下图所示:
<br/>![](http://m.qpic.cn/psc?/V14aMFsz1pP4hB/wZu0*zqyEz4NDRuTFUPfB3MVxhxwD57*rwGHiNiGyQ*z.G9iiB8ThtfrDcfrOJgaw*K1ZFszONIrGn3EcA.aXw!!/mnull&bo=OQXjAgAAAAARB.0!&rf=photolist&t=5)
<br/>&emsp;&emsp;这样布线目的就是避免第一级交换机一旦出现问题无法继续工作，同级的另一个第一级交换机可以确保网络不致中断，可以使整个网络继续正常运转。所以这样用两台第一级交换机布线比只用一台第一级交换机更具有可靠性和稳定性，并且也相应的减小了第一级交换机工作的负担，能够充分利用网络资源。使整个网络发挥它的最大功效。
<br/>(2) 以我所在宿舍楼6号楼为例，其具体布线情况如下:
<br/>&emsp;&emsp;本楼有六层，利用一个8口的自适应交换机(即第二级交换机)就能够满足本楼的需求。楼内各层有30个房间，也就需要至少30个接入点，所以一个交换机不够，需要两个交换机，即第三极交换机。
<br/>(3) 余下5栋楼结构相同，所以采用相同的布线结构。
<br/>&emsp;&emsp;其拓扑结构如下图所示:
<br/>![](http://m.qpic.cn/psc?/V14aMFsz1pP4hB/wZu0*zqyEz4NDRuTFUPfB9FdRnBebvetVpuREDw9qGf9YdAXRxFiFCLAT9.XTA.riobiyR*wAIJaxtwQrKRtDg!!/mnull&bo=igJ8AooCfAIRCT4!&rf=photolist&t=5)
<br/>(4) 在每一栋学生公寓里每层30个宿舍，因此每层用2个16口的自适应交换机就能满足现在的需求，但为了方便以后网络的拓展应用，提高网络的可扩展行，选用一个16口的自适应交换机和一个24口的自适应交换机进行网络的连接拓展，除去和第二级交换机连接的接口，这样就总共有38个口可以利用，现在需要用到30个，余下8口方便以后的拓展。这样，一栋楼就余下了48个口。
<br/>&emsp;&emsp;每层楼的拓扑结构如下图所示:
<br/>![](http://m.qpic.cn/psc?/V14aMFsz1pP4hB/wZu0*zqyEz4NDRuTFUPfB6xgs8GCCPZeG1*2jTqy1HPxP*w1NhiAutXPU77b3wvlUwTpplrH1reqfwsRS6340Q!!/mnull&bo=hQTVAoUE1QIRCT4!&rf=photolist&t=5)
4. 网络拓扑硬件配置
<br/>第一级交换机:网络拓扑中第一级交换机选用万兆核心交换机RG-S6806。
<br/>第二级交换机:在楼栋接入的第二级交换机我们选用STAR-S3550系列三层交换机。
<br/>第三级交换机:第三极交换机我们选用锐捷网络的支持802.1x的千兆智能交换机RG-S2126G/2150G。
<br/>安全计费:方案选用基于802.1x技术的SAM系统结合接入层S2126G/S2150G交换机对学生接入控制进行管理。
<br/>网络管理:为了对整个网络的设备进行管理，建议配置STAR View网管系统。
5. IP地址分配
<br/>学生公寓6幢，每幢公寓六层，每层有30个房间，共有宿舍1080间。在此基础上，进行地址划分。
<br/>为了保证扩展性和安全性，对每栋楼的每层划分一个子网，为节省地址资源，选择每层楼地址连续，进行详细的子网划分，保证每个宿舍接入一个信息点，剩余地址资源留做扩展用途。
<br/>&emsp;&emsp;具体的地址分配方案和子网划分方案如下:
<br/>&emsp;&emsp;1号公寓:192.168.0.0-192.168.0.255
<br/>其中各层楼可均分这254个地址（除去两个特殊地址），所以各楼层地址分配如下：
<br/>&emsp;&emsp;一楼:192.168.0.1-192.168.0.30
<br/>&emsp;&emsp;二楼:192.168.0.31-192.168.0.60
<br/>&emsp;&emsp;三楼:192.168.0.61-192.168.0.90
<br/>&emsp;&emsp;四楼:192.168.0.91-192.168.0.120
<br/>&emsp;&emsp;五楼:192.168.0.121-192.168.0.150
<br/>&emsp;&emsp;六楼:192.168.0.151-192.168.0.180
<br/>这样还余下74个地址没有分配，留待应急。
<br/>2号公寓:192.168.1.0-192.168.1.255
<br/>&emsp;&emsp;一楼:192.168.1.1-192.168.1.30
<br/>&emsp;&emsp;二楼:192.168.1.31-192.168.1.60
<br/>&emsp;&emsp;三楼:192.168.1.61-192.168.1.90
<br/>&emsp;&emsp;四楼:192.168.1.91-192.168.1.120
<br/>&emsp;&emsp;五楼:192.168.1.121-192.168.1.150
<br/>&emsp;&emsp;六楼:192.168.1.151-192.168.1.180
<br/>3号公寓:192.168.2.0-192.168.2.255
<br/>&emsp;&emsp;一楼:192.168.2.1-192.168.2.30
<br/>&emsp;&emsp;二楼:192.168.2.31-192.168.2.60
<br/>&emsp;&emsp;三楼:192.168.2.61-192.168.2.90
<br/>&emsp;&emsp;四楼:192.168.2.91-192.168.2.120
<br/>&emsp;&emsp;五楼:192.168.2.121-192.168.2.150
<br/>&emsp;&emsp;六楼:192.168.2.151-192.168.2.180
<br/>4号公寓:192.168.3.0-192.168.3.255
<br/>&emsp;&emsp;一楼:192.168.3.1-192.168.3.30
<br/>&emsp;&emsp;二楼:192.168.3.31-192.168.3.60
<br/>&emsp;&emsp;三楼:192.168.3.61-192.168.3.90
<br/>&emsp;&emsp;四楼:192.168.3.91-192.168.3.120
<br/>&emsp;&emsp;五楼:192.168.3.121-192.168.3.150
<br/>&emsp;&emsp;六楼:192.168.3.151-192.168.3.180
<br/>5号公寓:192.168.4.0-192.168.4.255
<br/>&emsp;&emsp;一楼:192.168.4.1-192.168.4.30
<br/>&emsp;&emsp;二楼:192.168.4.31-192.168.4.60
<br/>&emsp;&emsp;三楼:192.168.4.61-192.168.4.90
<br/>&emsp;&emsp;四楼:192.168.4.91-192.168.4.120
<br/>&emsp;&emsp;五楼:192.168.4.121-192.168.4.150
<br/>&emsp;&emsp;六楼:192.168.4.151-192.168.4.180
<br/>6号公寓:192.168.5.0-192.168.5.255
<br/>&emsp;&emsp;一楼:192.168.5.1-192.168.5.30
<br/>&emsp;&emsp;二楼:192.168.5.31-192.168.5.60
<br/>&emsp;&emsp;三楼:192.168.5.61-192.168.5.90
<br/>&emsp;&emsp;四楼:192.168.5.91-192.168.5.120
<br/>&emsp;&emsp;五楼:192.168.5.121-192.168.5.150
<br/>&emsp;&emsp;六楼:192.168.5.151-192.168.5.180
6. IP地址分配方案分析
<br/>&emsp;&emsp;该方案所用的地址段为192.168.0.0-192.168.5.255，子网掩码为255.255.255.0。6栋楼共分配了6个子网，一栋楼包含的256个地址，每个楼层分配30个地址。总共可利用地址数目为1524个，实际利用的地址数目为1080个，地址利用率约为70.87%。
<br/>&emsp;&emsp;该方案的地址段较宽，可利用的网络地址较多。并且子网络地址在各个楼层分布较为均匀，这样就使每个楼栋的可拓展性得到相应的提高，不存在不可拓展网络的问题。因为在学校公寓里，拓展性相对要求较高，而每幢楼还有74个IP地址未分配，可供将来扩展。网络管理可以只针对一个楼栋，如无特别要求无需对每个楼层进行管理。
7. Cisco Packet Tracer
<br/>&emsp;&emsp;PC机、服务器、路由器、交换机等设备模拟连接图：
<br/>![](http://m.qpic.cn/psc?/V14aMFsz1pP4hB/wZu0*zqyEz4NDRuTFUPfB60xo2I1n9eRKU1lycRypD74B5nISICKIpId1Z3nNbnOyYn1HoDZLpZyPLiRXaqqXA!!/mnull&bo=OwMUAzsDFAMRCT4!&rf=photolist&t=5)
8. 关键代码
<br/>1)交换机：
<br/>Switch>enable
<br/>Switch#configure terminal
<br/>Enter configuration commands, one per lineEnd with CNTL/Z.
<br/>Switch(config)#
<br/>%LINK-5-CHANGED: Interface FastEthernet0/4, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/4, changed state to up
<br/>%LINK-5-CHANGED: Interface FastEthernet0/5, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/5, changed state to up
<br/>%LINK-5-CHANGED: Interface FastEthernet0/6, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/6, changed state to up
<br/>%LINK-5-CHANGED: Interface FastEthernet0/7, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/7, changed state to up
<br/>%LINK-5-CHANGED: Interface FastEthernet0/8, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/8, changed state to up
<br/>%LINK-5-CHANGED: Interface FastEthernet0/9, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/9, changed state to up
<br/>Switch con0 is now available
<br/>2）路由器：
<br/>Router>enable
<br/>Router#configure terminal
<br/>Enter configuration commands, one per line.
<br/>End with CNTL/Z.
<br/>Router(config)#interface FastEthernet0/0
<br/>Router(config-if)#ip address 192.168.1.10 255.255.255.0
<br/>Router (config-if)#
<br/>Router(config-if)#exit
<br/>Router(config)#interface FastEthernet0/1
<br/>Router(config-if)#ip address 192.168.2.10 255.255.255.0
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/0
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/1
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config)#interface FastEthernet0/0
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/1
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/0
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/1
<br/>Router(config-if)#
<br/>Router(config-if)#exit
<br/>Router(config) #interface FastEthernet0/0
<br/>Router(config-if) #no shut down
<br/>Router(config-if)#
<br/>%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
<br/>%LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/0, changed state to up
<br/>Router(config-if)#exit
<br/>Router(config)#interface FastEthernet0/1
<br/>Router (config-if) #no shut down
9. 设计分析
<br/>1)可用性和可靠性
<br/>&emsp;&emsp;第一级交换机采用的双交换机方式,可以保证这个网络的可用性和可靠性，确保在第一级交换机出现问题不至于使整个网络停止工作。通过校园网与Internet相连，安全性得到保证。
<br/>2)安全性和易管理性
<br/>&emsp;&emsp;完满解决IP地址冲突和IP地址盗用。对于安全性，通过学生宿舍公寓的区域划分和高层对校园网安全设备的共享来逐级实现网络的安全性。对内的安全实施包括用交换机进行VLAN的划分，在路由中创建访问控制列表，如此可对一些网络用户实行可控的安全级别。
<br/>3)后续可扩展性
<br/>&emsp;&emsp;由于计算机的不断发展，网络系统必然需要扩大。本设计从网络拓扑布线设计到IP地址的设计都充分考虑到后续的可拓展性。在第一级交换机，第二级交换机，第三极交换机出都留有足够的接口用于以后的拓展，在进行IP地址的设计时也考虑到这一点。
### 五、课程设计总结
<br/>&emsp;&emsp;这几天的课设过程，我也学习到许多新的技能，比如对git和GitHub的了解，以及对markdown编辑器的运用。在一开始的时候，确实感觉无从下手，但是看完相关资料与教程后，我一步步慢慢来，也逐渐上手了。在此过程中，我也遇到过问题，比如图片在markdown中显示不了，通过查阅资料以及老师和同学的帮助，我顺利解决了这个问题。我也进一步了解到学生公寓的拓扑结构，明白我们所学知识都要与实际相结合，这样才能把所学运用到实处，所以，一切都要从实际情况出发！
<br/>&emsp;&emsp;通过本次网络工程与组网课程设计，我对计算机网络的理解更加深刻，对于网络的划分也有了更多的了解。我也明白一个学校的网络设计非常复杂，需要考虑到方方面面，不仅在当下，还要放眼于未来！
### 六、参考文献
<br/>[1]Markdown的常用语法(个人总结)[EB/OL].https://www.jianshu.com/p/82e730892d42
<br/>[2]Git和GitHub使用教程[EB/OL].https://www.jianshu.com/p/296d22275cdd
<br/>[3]GIT版本管理看这一篇就够了[EB/OL].https://www.jianshu.com/p/0e9d07ec76f9
<br/>[4]谢希仁.计算机网络（第5版）[M].北京:电子工业出版社.2008年1月
#### 本文档地址：https://github.com/MWY-9/network_design/blob/master/network_design_%E9%A9%AC%E6%96%87%E9%A2%96_175260612.md
