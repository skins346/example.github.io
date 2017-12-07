---
layout: post
title: 打造博客站点之旅(全记录)
category: blog
tag: blog
---
![一直在寻找，一直在编程](http://upload-images.jianshu.io/upload_images/4455053-537d622813d33902.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
>最近心情不大好，诸多事情都让人显得精疲力竭，毫无生机。我知道很多人可能都和我一样，在孤独的城市一直在孤独的坚持着做孤独的事。时间一久，怀疑这种状态和追求的价值的情绪就慢慢浮在每一个早晨，回家的路上，等车的时候，晚上睡觉的时候。这当中意义究竟何在。
 这个过程中看了一些解决拖延症，时间管理，个人管理的文章，[知乎：如何解决拖延症](https://www.baidu.com/link?url=m_egjSpMgGZhEY8LMZ3qcrwc_niBRyQ9zD1da0ljaKFGyXU_3uzZvKQuGH34sqBsbxzcLltd4y8GR9V-7uXA5a&wd=&eqid=86c395e700003e1e000000065966d9ea) ,还有 [简书：如何成为快乐高产的程序员](http://www.jianshu.com/p/7c4fcd8ac19e).写得不错，里面连带了些个人管理，习惯养成。这些文章稍许给了我继续下去的勇气与动力。

回到正题，建立自己的博客或者说个人站点其实成为很多程序员喜欢做的事。原因有很多，我想其中最主要的原因就是能够记录下自己工作轨迹与内容。于是乎，我们也会去记录下自己的心情，观点，想法，日记，游记等等。大部分的程序员大牛都有自己的网址或者个人站点，把内容当成一种财富或者产品，是这个时代越来越重视的地方。本坑从0开始自己建立博客网站，记录在此，希望能给一些想自己建立网站的新手们多一些可以借鉴的资料。如果有错，记得评论告诉本坑。以后本坑的简书的内容也会出现在个人站点内，欢迎关注和点赞。[本坑的博客地址](http://zivenday.me)

>接下来的过程需要你具有一定的动手能力，本坑操作电脑为Mac，同时你将会了解到[markdown](http://www.appinn.com/markdown/)，[github pages](https://pages.github.com/)，[Jekyll](http://jekyllrb.com/)，[Liquid基础语法](http://www.cnblogs.com/lslvxy/p/3651936.html)等等。这些内容如果有些你并不了解，没关系，只需要你在下面阅读遇到时及时查阅了解，直到你把自己的博客站点建立并运用为止。所以本坑都当你了解以上内容，以此记录说明。

######有哪些方式去建立自己的站点呢？
有很多方式，现在比较流行的工具有[WordPress](https://cn.wordpress.org/)，有jekyll+github pages。当然也有其他建站工具，比如，hexo+github pages，不过这里都不去提了。你也可以手动搭建一个服务器或者租赁服务器，运行一套自己写的程序系统，建立自己的博客站点。毫无疑问，我们都是新手，我们更喜欢更加快捷和方便的方式。
     那么wordpress和jekyll+github pages有什么区别呢？jekyll是基于html+MarkDown的博客生成方式。他强调的静态网页的生成。你只需要运用简单的markdown去书写自己博客内容，jekyll自动将其转出html，展示到世人面前。如果把整个系统上传到github ，由于github pages 整合了jekyll ，它将像在本地一样识别静态文件并且运行起来。wordpress是动态，就像我们自己编程一样，它是基于php/mysql的动态生成方式，有数据库的存在必然数据不是静态的，相比前者，WordPress站点结构显得更加自动，清晰。但是这并不意味前者不自动，也不清晰，只是相对比起来而已。本坑采用的jekyll方式去建站，一来它还有比较方便的内容书写体验，二来它结合github。如果这并不是你想要的方式，可能接下来你就没有必要再阅读下去。
对于大多数想拥有自己站点的盆友，都希望有个性化的域名，邮箱等等。博客域名也如此。如果你要做到这些，就得去申请这些。域名申请值得推荐的有[godaddy](https://sg.godaddy.com/zh?tmskey=1dom_23&isc=gennbacn03&countrview=1&currencytype=CNY&cvosrc=ppc.baidu&mkwid=1edNUgIP8_pcrid_10564083847_pdv_c),也有阿里云等等，有了域名还不够，你还得设置一个域名解析服务器去解析申请的域名。本坑使用的是国内的[dnspod](https://www.dnspod.cn/)。说到这里是否觉得很麻烦？其实这些内容，所有的这些实际操作都并非难事，本坑也会进行介绍解释。域名解析设置和github pages 绑定个性域名，这个将在本地站点搭建完成之后提到。

######jekyll+github建立空白博客站点
糊涂的你可能觉得域名不域名的让人烦。先不管这些，先把具体博客站点框架本地搭起来吧。我们知道jekyll是一个静态的博客站点生成器，它的构建语言是ruby，Gem是封装起来的Ruby应用程序或代码库,在终端使用的gem命令，是指通过RubyGems管理Gem包。所以，你必须在安装jekyll前先安装ruby，如果电脑中没有安装过ruby的话。
<pre>ruby官网下载传送门：https://www.ruby-lang.org/en/downloads/
ruby版本检测指令：ruby --version
jekyll 安装: sudo gem install jekyll
jekyll 版本检测指令：jekyll -v
jekyll 服务启动指令：jekyll serve
</pre>

![安装后生成的jekyll目录](http://upload-images.jianshu.io/upload_images/4455053-1e64105bbf7749ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
启动jekyll后，运行http://127.0.0.1:4000/  你将会知道是否可以使用这个博客站点


![目录结构 说明](http://upload-images.jianshu.io/upload_images/4455053-53079708acee2a3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


######使用完整功能的站点模板
[jekyll模板](http://jekyllthemes.org/)是非常丰富的，如何使用这些模板呢?很简单，暴力下载，直接运行就行了，本坑使用的是[Codinfox Lanyon](http://jekyllthemes.org/themes/codinfox-lanyon/)。要如何转换成你自己的博客网站，你就得先从_config.yml开始。这里不再赘述。
>本坑测试发现，codinfox-lanyon的评论功能存在问题，要下载的要注意了。同时在更改配置信息时，baseurl需要改成“”,才能在github pages上正常运行。

此时，我们在gihub中要做如下几件事
1、github你需要申请一个仓库，名字为'用户名.github.io',
2、把整个模板上传到这个github这个仓库当中。
3、打开这个仓库的setting，像以下图一样设置。


![github pages 设置](http://upload-images.jianshu.io/upload_images/4455053-3f3175a20a1415c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
等过几分钟，刷新设置页面，该页面会显示是否设置成功。由于我绑定了域名，我的显示如下图所示。[本坑的博客地址](http://zivenday.me)

![渲染成功](http://upload-images.jianshu.io/upload_images/4455053-24b66e9898fa7400.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




######域名解析配置与github pages 域名绑定
本坑申请的域名为ziven.me，同时前面提到本坑使用的是dnspod来解析域名。如下两张图，其中CNAME可以不用设置。注意了，godaddy也要设置域名解析服务器就是第二张图默认的两个记录值。

![对应域名](http://upload-images.jianshu.io/upload_images/4455053-365815c19baa0b65.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![对应到github pages IP](http://upload-images.jianshu.io/upload_images/4455053-e5d6e4464477cd17.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
以上两张图里的数据都是处在同一个表格内，以上的各行各列是什么意思呢？
  A (Address) 记录是用来指定主机名（或域名）对应的IP地址记录。
    A记录设置方法
    1、如果想创建不带www的记录，即abc.com，在主机记录中填写@或者留空。
    2、创建多个域名到同一个IP，比如给博客建了二级域名，可以使用*.blog.abc.com来指向一个IP，这样的话，不管是访问a.blog.abc.com还是b.blog.abc.com都能到同一个IP。
CNAME记录
    CNAME记录也称别名记录，它允许你将多个记录映射到同一台计算机上。具体就是你可以将一个域名做A记录指向服务器IP然后将其他的域名做别名记录到之前做A记录的域名上，那么当你的服务器IP地址变更时你就可以不必麻烦的一个一个域名更改指向了，只需要更改做A记录的那个域名其他做别名记录的那些域名的指向也将自动更改到新的IP地址上了。
ns 表示域名解析的服务器。
>而要github pages 绑定到指定域名就更简单了，在项目根目录新建CNAME文件，添加指定域名，比如本坑的是zivenday.me。github对应仓库setting的Custom domain设置成zivenday.me 点击保存，过几分钟就行了。

好了，到这里大致都已经说完了，本坑的博客站点在发表文章时才刚刚建立，除了基本信息更改后，样式都是模板的。该博客将会在将来做如下更改：
1、修改评论的功能；
2、添加赞和分享的功能；
3、首页添加内容轮播等等效果；
4、添加时间分类功能；
5、其他修改