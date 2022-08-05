---
title: 你说，什么是Cloudflare？
date: 
updata:
author: qunerCloud 
categories: # 分类
- 互联网
tags: # 标签
- CDN
- Cloudflare
- cf
description:
top_img: https://s2.loli.net/2022/07/23/fKZ8FirHowlSL6U.png
cover: https://s2.loli.net/2022/07/23/fKZ8FirHowlSL6U.png
copyright: false
toc:
toc_number:
toc_style_simple:
aplayer:
---

{% note blue no-icon %}
**转载自https://cn.quner.icu:8443/2022/07/22/%e4%bd%a0%e8%af%b4%ef%bc%8c%e4%bb%80%e4%b9%88%e6%98%afcloudflare%ef%bc%9f/**
{% endnote %}

![](https://s2.loli.net/2022/07/23/fKZ8FirHowlSL6U.png)

如果你刚开始接触Web，很多教程文档都会推荐你”套CF“。而当你在群里抱怨买的VPS线路不好，源站（存放Web文件）连接不稳定时，群友们肯定会让你”套个CF“。

可是，到底什么是CF？

当然，有些梗大师会这么解释这个问题：

![c7b39932a19cdb0f0f12e.png](https://s2.loli.net/2022/07/23/T7uInriZdzL5e3w.png)

以及：

![fe057bdbe6e5dd22b9948.png](https://s2.loli.net/2022/07/23/KdSPNiBv9bHDMXa.png)

————————————正文分割线————————————

”“Lee Holloway 编写出了Cloudflare。然后他变得冷漠，疏远，不可预测——很长一段时间，没有人能理解它。”

“ 100多名员工和投资者在下方交易大厅欢呼，他们的手机高高举起捕捉现场。11 号员工Kristin Holloway抬头看着阳台，拍了张照片，然后把它们做成了一条短信，发给了她的丈夫Lee Holloway。他在加利福尼亚的家中。每隔一段时间，就会有一张熟悉的面孔从人群中挤进来对她说：‘Lee应该在这里。’”

  

  

今天，我想和大家聊聊，什么是Cloudflare（CF），它为什么即使不是世界第一（Akamai）却在信息圈备受好评人尽皆知，以及Cloudflare背后的一些隐秘的角落。

关于Cloudflare，主营DNS（域名解析），CDN（内容分发）和Anti-DDOS（清洗流量）的一家良心企业。相比于世界第一的CDN厂商Akamai根本不toC（Akamai没有面向普通消费者的业务），Cloudflare提供给咱们普通人免费使用的机会。感情上，妥妥收割了一大批用户。如果是你，你会怎么想呢？

![114efa09354ee5c7eb322.png](https://s2.loli.net/2022/07/23/nURQTlqZCLfvmWa.png)

（Akamai，其根本不提供toC业务）

![1607e1d8cff3e1e67b2da.png](https://s2.loli.net/2022/07/23/9Ot1HRQhUNbPneD.png)

![e6675f50f356cb9522149.png](https://s2.loli.net/2022/07/23/hEYlBdmZvXiNo2k.png)

（Cloudflare，平易近人）

  

  

从19年到现在，我已经使用Cloudflare近3年了。它给我一种逐渐成长至茁壮的感觉，而且，它不叛逆。（不得不提国内阿\*云一再涨价，连当年支持的老用户还下刀）

举几个简单的例子：

首先：Web需要一个域名（Domain）。【简单来说，它是你的IP的一个好听的名字，就像IP是身份证号，而域名是姓名。除了重度开盒爱好者，相信应该没人用身份证号称呼别人。】而Cloudflare推出了”不加价“的注册域名服务，换言之，它不赚钱。（鞭尸国外Godad\*\*诱导欺诈）

PS.域名不会还有人在国内买，乖乖去实名认证备案吧.......

比如，以menggushangdan.com为例。

GoDad\*\*:

![932c76d69272abeaf1d0c.png](https://s2.loli.net/2022/07/23/k7cTw3Idi541SEZ.png)

(表面只要0.19,但必须一次购买两年，平均一年10.18USD)

  
Cloudflare:

![932c76d69272abeaf1d0c.png](https://s2.loli.net/2022/07/23/k7cTw3Idi541SEZ.png)

  
（真是个诚信的乖孩子，叔叔我啊，最喜欢CF了）

  

再者：Cloudflare著名的DNS1.1.1.1

从Web的角度，Cloudflare的DNS支持最短TTL到1Min，换句话，你的记录最慢1分钟就会生效。而实测一般10-15秒就生效了。比起某些DNS动辄10分钟的刷新时间，Cloudflare简直秒杀。

![99587cb3de4afd3270b43.png](https://s2.loli.net/2022/07/23/itP3Flm87AqjJNI.png)

（TTL，最小值1分钟）

  

而从使用者的角度，Cloudflare著名的1.1.1.1DNS，（除大陆以外）地区解析速度都是第一，远超Google8.8.8.8的DNS.（话说之前1.1.1.1似乎被江苏列入墙中墙名单，各位有感觉吗？）

![adc5f7abedfa8d1384fb8.png](https://s2.loli.net/2022/07/23/35umtORFDKvLc8E.png)

(来源：1.1.1.1）

至于什么Doh，Dot等，Cloudflare完全免费满血开放，而不像国内某Pod，竟然额外推出付费服务。

![2575150733c9ab8f8f125.png](https://s2.loli.net/2022/07/23/OjAYNHcGxSMI4R2.png)

接着看Cloudflare最受人欢迎的功能，免费CDN。还是之前那张图，看到橙色小云朵吗？代表Cloudflare将调用他全世界的服务器（未备案则大陆除外）帮你分发网站，减少延迟。其使用泛播技术，保证终端优先接触最近的Cloudflare节点，再由CF内部网络完成全世界的转发。

比如，我的网站quner.cloud。

![9497a916b69dac406fad3.png](https://s2.loli.net/2022/07/23/GsnJFe9INMYcoyV.png)

我的主机在德国，如果没有CF，延迟大概在280ms左右，丢包率和响应速度都很拉跨。但套上CF之后，延迟下降到180ms（连接到他们洛杉矶机房，再由他们内部网路路由到当地CF服务器，再请求当地源站）。

![574f67adca3751cebe0cf.png](https://s2.loli.net/2022/07/23/QBaxLngcUYPVD89.png)

（测试在凌晨2点，如果白天能到380ms）

所以，应该有人听说过V2Ray+WS+CF这种对于垃圾线路的加速方式。而因为Cloudflare对于国内很多服务太重要了（大家都在引用套了CF的资源），使得GFW对于Cloudflare也无可奈何。基本上说，当你套了CF，你的VPS（在一直续费的情况下）可以作为传家宝了。

（另：关于代理协议，以后会写一篇更完整的。）

而Cloudflare不仅仅起到加速作用，它的DDOS抗打到什么程度，经常有笑话这么讲：

“我套CF了，希望你成为打穿CF的第一人。”

就是这么夸张，尽管就算是Mirai僵尸网络，也没把Cloudflare打穿。更何况普通人呢？但为什么经常听到群友抱怨：“我套了CF，还是被DDOS死了。”这是为什么呢？

“因为他们找到了你的源站IP，而你并没有限制除CF外禁止访问。”

话说到这里，我想低调宣布一件事情，你可以利用CF辅助渗透，寻找别人源站IP。

当你把域名添加进CF时，会不会发现它能自动扫描你的所有域名？

正是这个机制，可以很方便帮我们找旁站，排除掉搜出来是CF泛播的IP，剩下的就是源站IP。这种搜索非常精准，几乎所有常见的域名都可以搜到。例如blog.XXX.com或者repo.xxx.com什么的。

好不好奇他们怎么做的？CF在官网上表示：他们会对要添加的域名进行常见的前缀扫描。

![19bc430c1066040ae2f5b.png](https://s2.loli.net/2022/07/23/gyxZONM8rhqfJXi.png)

让我们选择一位幸运域名参与实验，比如我同学的某域名:xxxdnzj.com

示范一下标准操作：

![d7e5c3459ceb73a002c64.png](https://s2.loli.net/2022/07/23/x5vA4EwDTcJaGqo.png)

Inserting image...

排除CF的IP，67.230开头的那个IP就是他源站的IP了（用过BWH的就知道67.230这个IP段里面都是美西洛杉矶的CN2 GIA IP）

怎么样？神不神奇？

最后，我想以崇敬地态度，提一下CF的创始人之一： Lee Holloway

我看到最精准，也是最让人难过的评价是：

  

“The Devastating Decline of a Brilliant Young Coder

Lee Holloway programmed internet security firm Cloudflare into being. Then he became apathetic, distant, and unpredictable—for a long time, no one could make sense of it.”

“一个天才程序员的陨落。”

Lee Holloway早期可谓神话，在CF里编写蜜罐和流量清洗算法，无所不能。

“在 Cloudflare 的早年，Lee Holloway 一直是常驻天才，他可以集中注意力几个小时，代码从指尖倾泻而出，同时死亡金属在他的耳机中爆炸。他是一位伟大的建筑师，他的愿景将最初只是一张餐巾纸上的文字草图引导成一家拥有约 1,200 名员工和 83,000 名付费客户的科技巨头。他为现在处理超过 10% 的所有互联网请求并每天阻止数十亿网络威胁的系统奠定了基础。他梦想的大部分建筑仍然存在。”

“但在 IPO 前几年，他的行为开始发生变化。他对自己的项目和同事失去了兴趣。他在会议上不再专心。他的同事注意到他变得越来越僵化和好战，抵制别人的想法，无视他们的反馈。.......神经学家做出了他们的结论：他似乎患有额颞叶痴呆的教科书病例——简称 FTD——特别是这种疾病的行为变异。它针对的大脑区域网络有时被描述为支撑一个人的自我意识。随着病理过程的进展，它正在从李的原料中雕刻出一个不同的人。”

![6a6b790331d19ca590b01.png](https://s2.loli.net/2022/07/23/wUH3SL9flsqI5h8.png)

（ Lee Holloway 中）

“九月星期五2019 年 1 月 13 日，旧金山互联网安全公司 Cloudflare的联合创始人 Matthew Prince 和 Michelle Zatlyn站在一个细长的大理石阳台上，俯瞰纽约证券交易所的地板。一群公司高管站在普林斯附近，准备喊倒计时。“大声点！大声！” 王子催促他们。“五！四！三！……” 上午 9 点 30 分，创始人伸手敲响了交易所著名的钟声，开始了当天的交易，并将他们拥有 10 年历史的公司公开上市。这是一个成年礼，也是他们的发薪日，一个释放数百万美元新财富的时刻。  
“100多名员工和投资者在下方交易大厅欢呼，他们的手机高高举起捕捉现场。11 号员工克里斯汀·霍洛威（Kristin Holloway）抬头看着阳台，拍了张照片，然后把它们做成了一条短信，发给了她的丈夫李·霍洛威（Lee Holloway），他是公司的第三位联合创始人。他在加利福尼亚的家中。每隔一段时间，就会有一张熟悉的面孔从人群中挤进来对她说：“李应该在这里。”  
  
  
感谢观看！  
  
作者：[@qunerCloud](https://t.me/qunerCloud) | Web：[https://quner.cloud](https://quner.cloud/)

  
参考传记： [wired.com/story/lee-holloway-devastating-decline-brilliant-young-coder](https://www.wired.com/story/lee-holloway-devastating-decline-brilliant-young-coder/)

特别鸣谢：[@Shirker](https://t.me/Shirker)

首发于： [https://t.me/ShareCentre](https://t.me/ShareCentre)

并同步在个人博客[https://diary.quner.cloud](https://diary.quner.cloud/)中。