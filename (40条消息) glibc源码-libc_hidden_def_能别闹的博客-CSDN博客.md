# (40条消息) glibc源码-libc_hidden_def_能别闹的博客-CSDN博客
             (40条消息) glibc源码-libc\_hidden\_def\_能别闹的博客-CSDN博客      

[![](https://img-home.csdnimg.cn/images/20201124032511.png)
](https://www.csdn.net/)

*   [博客](https://blog.csdn.net/)
*   [下载](https://download.csdn.net/)
*   [学习](https://edu.csdn.net/)
*   [社区](https://bbs.csdn.net/)
*   [GitCode](https://gitcode.net?utm_source=csdn_toolbar)
*   [云服务](https://dev-portal.csdn.net/welcome?utm_source=toolbar)
*   [猿如意](https://devbit.csdn.net?source=csdn_toolbar)

搜索 

[![](https://profile.csdnimg.cn/9/A/2/2_qq_26713443)
](https://blog.csdn.net/qq_26713443)

[![](https://profile.csdnimg.cn/9/A/2/0_qq_26713443)
](https://blog.csdn.net/qq_26713443)

\--

[](https://mall.csdn.net/vip)

[_\--_粉丝](https://blog.csdn.net/qq_26713443?type=sub&subType=fans) [_\--_关注](https://blog.csdn.net/qq_26713443?type=sub) [_\--_获赞](https://blog.csdn.net/qq_26713443)

*   [个人中心](https://i.csdn.net/#/user-center/profile)
*   [内容管理](https://mp.csdn.net/mp_blog/manage/article?spm=1011.2124.3001.5298)
*   [我的学习](https://edu.csdn.net?utm_source=edu_txxl_mh)
*   [我的订单](https://mall.csdn.net/myorder)
*   [我的钱包](https://i.csdn.net/#/wallet/index)
*   [我的云服务](https://dev-portal.csdn.net/welcome?utm_source=toolbar_user_profile)
*   [我的认证](https://ac.csdn.net/user/myCert.html)
*   [签到抽奖](https://i.csdn.net/#/uc/reward)
*   [退出](javascript:;)

[会员中心 ![](https://img-home.csdnimg.cn/images/20210918025138.gif)](https://mall.csdn.net/vip) 

[足迹](https://i.csdn.net/#/user-center/collection-list?type=1)

[动态](https://blink.csdn.net)

[投票](https://blink.csdn.net/?source=vote)

[消息](https://i.csdn.net/#/msg/index)

[评论和@](https://i.csdn.net/#/msg/index) [新增粉丝](https://i.csdn.net/#/msg/attention) [赞和收藏](https://i.csdn.net/#/msg/like) [私信](https://im.csdn.net/im/main.html) [系统通知](https://i.csdn.net/#/msg/notice) [消息设置](https://i.csdn.net/#/msg/setting)

[创作中心 ![](https://img-home.csdnimg.cn/images/20220627041202.png)](https://mp.csdn.net/ "创作中心") 

[发布](https://mp.csdn.net/edit)

 

glibc源码-libc\_hidden\_def
=========================

![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[能别闹](https://blog.csdn.net/qq_29173507) ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCurrentTime2.png)
 于 2021-01-07 20:14:05 发布 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes2.png)
 1155 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect2.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollectionActive2.png)
 收藏  8 

分类专栏： [C语言](https://blog.csdn.net/qq_29173507/category_9816363.html) 文章标签： [glibc](https://so.csdn.net/so/search/s.do?q=glibc&t=blog&o=vip&s=&l=&f=&viparticle=)

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

本文链接：[https://blog.csdn.net/qq\_29173507/article/details/112324568](https://blog.csdn.net/qq_29173507/article/details/112324568)

版权

 [![](https://img-blog.csdnimg.cn/20201014180756927.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
   C语言 专栏收录该内容](https://blog.csdn.net/qq_29173507/category_9816363.html "C语言") 

15 篇文章 0 订阅

订阅专栏

glibc版本：2.32  
在阅读scanf[源码](https://so.csdn.net/so/search?q=%E6%BA%90%E7%A0%81&spm=1001.2101.3001.7020)的时候，看到ldbl\_hidden\_def，不明这个宏的意思，于是查阅资料，进行了一番了解。(  
因为涉及的知识点太过庞大，包含链接，库的加载，函数的调用等等，且当前不从事与这方面的研究，故仅了解下)

**原创文章，转载请备注**:[https://blog.csdn.net/qq\_29173507/article/details/112324568](https://blog.csdn.net/qq_29173507/article/details/112324568)  
![](https://img-blog.csdnimg.cn/20210107174103194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20210107174202461.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)
  
scanf调用：scanf->\_\_vfscanf\_internal.  
\_\_vfscanf\_internal的实现代码有2700行。。。。恐怖。浏览了一遍，没完全读懂，和vfprintf差不多，找到格式化字符，然后调用系统接口读入信息，并复制给变参的变量。

好奇看了下vfscanf，发现中间的宏看不懂  
![](https://img-blog.csdnimg.cn/20210107174124819.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)

**原创文章，转载请备注**:[https://blog.csdn.net/qq\_29173507/article/details/112324568](https://blog.csdn.net/qq_29173507/article/details/112324568)

### **ldbl\_hidden\_def (\_\_\_vfscanf, \_\_vfscanf)**

ldbl\_strong\_alias和ldbl\_weak\_alias两个宏展开后，是使用attribute关键字对函数名进行别名声明，强别名和弱别名的区别；ldbl\_hidden\_def 展开后发现跟attribute也有关系，挺有意思的。  
![](https://img-blog.csdnimg.cn/20210107175040791.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)

ldbl\_hidden\_def (\_\_\_vfscanf, \_\_vfscanf) -> libc\_hidden\_def(\_\_vfscanf)  
![](https://img-blog.csdnimg.cn/20210107174900454.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)

### **libc\_hidden\_def的作用**

继续探索libc\_hidden\_def，在头文件libc-symbols.h中找到这个说明。  
![](https://img-blog.csdnimg.cn/20210107182137738.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)
  
可以看到libc\_hidden\_proto和libc\_hidden\_def成对出现的，跟PLT相关。找了半天，在  
stack-overflow找到  
[https://stackoverflow.com/questions/37290230/what-does-libc-hidden-proto-in-the-glibc-standard-libraries-do](https://stackoverflow.com/questions/37290230/what-does-libc-hidden-proto-in-the-glibc-standard-libraries-do)  
![](https://img-blog.csdnimg.cn/20210107182451789.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)
  
可以看到和这些知识相关。可以看这个博文了解下。  
[浅析ELF中的GOT与PLT](https://blog.csdn.net/u011987514/article/details/67716639?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromBaidu-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromBaidu-1.control)

通读后就会发现libc\_hidden\_def的**作用**:  
标志修饰的函数在动态链接的过程中进行延迟绑定。  
**好处**就是，只有该函数在调用到的时候才进行地址绑定，如果整个执行过程中没有用到该函数就不需要绑定，会大大节约系统资源。

### libc\_hidden\_def的实现

继续追踪libc\_hidden\_def的实现代码  
![](https://img-blog.csdnimg.cn/20210107200656613.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)
  
看上面的预编译指令，走的上面这个分支 # define rtld\_hidden\_def(name) hidden\_def (name)。继续跟踪。

![](https://img-blog.csdnimg.cn/20210108164855621.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5MTczNTA3,size_16,color_FFFFFF,t_70)
  
当然是走的非汇编的分支咯，可以看到跟attribute关键字是有相关的，做了两步操作。

**原创文章，转载请备注**:[https://blog.csdn.net/qq\_29173507/article/details/112324568](https://blog.csdn.net/qq_29173507/article/details/112324568)

 

[![](https://profile.csdnimg.cn/B/6/C/3_qq_29173507)
能别闹](https://blog.csdn.net/qq_29173507)

[关注](javascript:;) 关注

*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarThumbUpactive.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2021Active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newHeart2021Black.png)
      2 
    
    点赞
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newUnHeart2021Active.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newUnHeart2021Black.png) 
    
    踩
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollectionActive.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCollectBlack.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCollectActive.png)
      8](javascript:;) 
    
    收藏
    
*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/newRewardBlack.png)](javascript:;) 
    
    打赏
    
*    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newComment2021Black.png)
     1 
    
    评论
    

*    [![](https://csdnimg.cn/release/blogv2/dist/pc/img/newShareBlack.png)](javascript:;) 
    
    ![](https://profile.csdnimg.cn/B/6/C/3_qq_29173507)
    
    glibc源码-libc\_hidden\_def
    
    glibc版本：2.32在阅读scanf源码的时候，看到ldbl\_hidden\_def，不明这个宏的意思，于是查阅资料，进行了一番了解。(因为涉及的知识点太过庞大，包含链接，库的加载，函数的调用等等，且当前不从事与这方面的研究，故仅了解下)scanf调用：scanf-&gt;vfscanf-&gt;\_\_vfscanf\_internal.\_\_vfscanf\_internal的实现代码有2700行。。。。恐怖。浏览了一遍，没完全读懂，和vfprintf差不多，找到格式化字符，然后调用系统接口读入信
    
    复制链接
    
    扫一扫
    
    热门
    
    VIP
    

专栏目录

[

_glibc__源码_下载

](https://blog.csdn.net/weixin_30832143/article/details/98548475)

[weixin\_30832143的博客](https://blog.csdn.net/weixin_30832143)

04-19 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 885 

[

https://www.gnu.org/software/_libc_/ Download sources Releases are available by source branch checkoutvia gitand tarballvia ftp. Checkout the latest _glibc_ 2.27 stable release: git clone git://sou...

](https://blog.csdn.net/weixin_30832143/article/details/98548475)

[

_glibc_升级导致系统段错误问题解决方案

最新发布

](https://blog.csdn.net/bubbleyang/article/details/128016448)

[bubbleyang的博客](https://blog.csdn.net/bubbleyang)

11-24 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 18 

[

内核实现一个功能，_glibc_要花很久才会用上，由于_glibc_和内核不是一块开发的，所以_glibc_需要去兼容不同版本的内核，而内核也要去兼容不同版本的 _glibc_，双方都背负了太多的历史包袱。总结： _GLIBC_是系统底层依赖的文件，自己不要随随便便编译，如果真要升级，那就使用yum升级，不要自己编译，因为编译出来的版本和内核版本之间不一定能兼容在一起，这是个很麻烦的事。当时以为是_GLIBC_库版本过低，于是自己就下载了_GLIBC_2.19版本的开始编译，编译过程不再赘述。二，升级_GLIBC_原因。

](https://blog.csdn.net/bubbleyang/article/details/128016448)

评论1条![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowRightWhite.png)
写评论

[![](https://profile.csdnimg.cn/6/A/B/3_u010330109)
远远看看山](https://blog.csdn.net/u010330109)热评

优秀，心血来潮研究这个也遇到了困惑，博主厉害

评论

写评论

[

c语言strcat源代码,【c语言】strcat源代码

](https://blog.csdn.net/weixin_29501693/article/details/117203532)

[weixin\_29501693的博客](https://blog.csdn.net/weixin_29501693)

05-23 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 353 

[

/\*\* Copyright (C) 1991, 1997, 2003 Free Software Foundation, Inc.This file is part of the GNU C Library.The GNU C Library is free software; you can redistribute it and/ormodify it under the terms of t...

](https://blog.csdn.net/weixin_29501693/article/details/117203532)

[

strmcp函数C语言,strcmp

](https://blog.csdn.net/weixin_42322686/article/details/117648817)

[weixin\_42322686的博客](https://blog.csdn.net/weixin_42322686)

05-28 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 147 

[

strcmp函数是string compare(字符串比较)的缩写，用于比较两个字符串并根据比较结果返回整数。基本形式为strcmp(str1,str2)，若str1=str2，则返回零；若str1str2，则返回正数。\[1-2\]中文名strcmp外文名strcmp类别库函数功能比较字符串s1和s2头文件一般形式strcmp(字符串1，字符串2)strcmp语法编辑externi...

](https://blog.csdn.net/weixin_42322686/article/details/117648817)

[

_glibc__源码_下载&在线阅读地址

](https://moddemod.blog.csdn.net/article/details/104681190)

[、moddemod](https://blog.csdn.net/weixin_43833642)

03-05 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 4560 

[

_glibc__源码_下载地址 http://ftp.gnu.org/pub/gnu/_glibc_/ http://www.gnu.org/software/_libc_/_libc_.html http://mirrors.nju.edu.cn/gnu/_libc_/ http://ftp.ntu.edu.tw/gnu/_glibc_/ http://mirrors.syringanetworks.net/gnu/lib...

](https://moddemod.blog.csdn.net/article/details/104681190)

[

_glibc_字符串小函数

](https://blog.csdn.net/u010451480/article/details/8957318)

[大风流的专栏](https://blog.csdn.net/u010451480)

05-21 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 456 

[

1.  strlen函数     自己先写一个看看：     版本一 int strlen(const char \*str) {     int len = 0;     const char \*p = str;     while(\*(p++) != '\\0')         ++len;     return len; } 版本二 int strlen(const

](https://blog.csdn.net/u010451480/article/details/8957318)

[

_libc_\__hidden_\__def_、_libc_\__hidden_\_weak、_libc_\__hidden_\_proto

](https://blog.csdn.net/weixin_45206746/article/details/117642974)

[私のBookShelf](https://blog.csdn.net/weixin_45206746)

06-07 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1021 

[

_libc_\__hidden_\__def_、_libc_\__hidden_\_weak、_libc_\__hidden_\_proto 在阅读_glibc__源码_的时候，遇见了几个没见过的宏，几乎所有的函数都会使用这几个宏：_libc_\__hidden_\__def_、_libc_\__hidden_\_weak、_libc_\__hidden_\_proto 因为我比较好奇，所以特地去找了一下有关这些宏的定义（主要也是想多学一点） Linux下学习_源码_，最方便的地方就是它的各种命令 使用find ./ | grep -r "_def_ine _libc_\__hidden_\__def_"，发现在in

](https://blog.csdn.net/weixin_45206746/article/details/117642974)

[

_glibc_ sprintf_源码_梳理（上）

](https://blog.csdn.net/u010330109/article/details/123272986)

[舍本逐末](https://blog.csdn.net/u010330109)

03-04 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 368 

[

尝试阅读sprint_源码_ _glibc_ 版本2.11 0. sprintf和snprintf sprintf和snprintf的是字符串格式化方法，可将格式化数据写入字符串中。 snprintf规定了写入字符串的最大长度，避免字符串长度溢出 sprintf和snprintf方法定义在libio/stdio.h中，其声明和方法参数说明如下： /\* \_\_s : 字符数组指针，存储拼接后的字符串 \_\_format: 字符串，规定了字符串格式 ... : 可变参数，填充format中的值

](https://blog.csdn.net/u010330109/article/details/123272986)

[

scanf_源码_分析

](https://blog.csdn.net/chennbnbnb/article/details/109601710)

[chennbnbnb的博客](https://blog.csdn.net/chennbnbnb)

12-02 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 671 

[

本文分析的是_glibc_2.31中的scanf相关_源码_，目的不是研究scanf的算法，而是说明scanf在IO attack中的利用方法，属于CTF的范畴 scanf.c 其实就是对\_\_vscanf\_internal的封装 \_\_scanf (const char \*format, ...) { va\_list arg; int done; va\_start (arg, format); done = \_\_vfscanf\_internal (stdin, format, arg, 0)

](https://blog.csdn.net/chennbnbnb/article/details/109601710)

[

_glibc__源码_解读——malloc

](https://blog.csdn.net/u010129119/article/details/77937207)

[Joe's Blog](https://blog.csdn.net/u010129119)

09-11 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2129 

[

通过宏定义的展开，找到malloc的函数地址： # _def_ine C\_SYMBOL\_NAME(name) name # _def_ine ASM\_LINE\_SEP ; void \*\_\__libc_\_malloc (size\_t bytes); _libc_\__hidden_\__def_ (\_\__libc_\_malloc) # _def_ine _libc_\__hidden_\__def_(name) _hidden_\__def_ (nam

](https://blog.csdn.net/u010129119/article/details/77937207)

[

_glibc_源代码的阅读

](https://blog.csdn.net/sulit/article/details/25539215)

[sulit的专栏](https://blog.csdn.net/sulit)

05-11 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 7329 

[

这两天在看gnu的c语言基本库，gangkaishi

](https://blog.csdn.net/sulit/article/details/25539215)

[

如何下载查看_glibc_源代码

热门推荐

](https://blog.csdn.net/Lucien_zhou/article/details/68568851)

[Lucien\_zhou的专栏](https://blog.csdn.net/Lucien_zhou)

03-30 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1万+ 

[

如何下载_glibc_源代码

](https://blog.csdn.net/Lucien_zhou/article/details/68568851)

[

C标准库_源码_解剖(5)：字符串处理函数string.h和wchar.h(续)

](https://blog.csdn.net/zhoudaxia/article/details/4641711)

[Jack Zhou的专栏](https://blog.csdn.net/zhoudaxia)

10-08 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 2599 

[

    3、字符串复制strcpy,strncpy,wcscpy,wcsncpy：将字符串src（或其前n个字符）复制到dest中，覆盖dest的内容。实现中先检查指针是否越界，计算指针dest到src的偏移，然后开始做复制操作，复制到dest的开始位置处，以覆盖dest的内容。对strncpy，也采用了每4个字符作为一组来进行复制的方法，以加快复制速度。/\* strcpy.c：strcpy函

](https://blog.csdn.net/zhoudaxia/article/details/4641711)

[

ARM Linux系统调用的原理

](https://blog.csdn.net/hongjiujing/article/details/6831192)

09-28 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 4636 

[

ARM Linux系统调用的原理 操作系统为在用户态运行的进程与硬件设备进行交互提供了一组接口。在应用程序和硬件之间设置一个额外层具有很多优点。首先，这使得编程更加容易，把用户从学习硬件设备的低级编程特性中解放出来。其次，这极大地提高了系统的安全性，因为内核在试图满足某个请求之

](https://blog.csdn.net/hongjiujing/article/details/6831192)

[

memstr

](https://blog.csdn.net/lisunlin0/article/details/6294025)

[Dustfly的专栏](https://blog.csdn.net/lisunlin0)

04-01 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 4722 

[

好长时间没有写过Blog了，呵呵在_glibc_里面有memchr,却没有memstr,发个memstr出来：/\* Return the offset of one string within another.    Copyright (C) 1994,1996,1997,2000,2001,2003 Free Software Foundation, Inc.    This file is part of the GNU C Library.    The GNU C Library is free

](https://blog.csdn.net/lisunlin0/article/details/6294025)

[

vfscanf

](https://blog.csdn.net/Michaelwubo/article/details/41444929)

[码农崛起](https://blog.csdn.net/Michaelwubo)

11-24 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 529 

[

相关函数：scanf, sscanf, fscanf 头文件：#include 定义函数：int vfscanf(FILE \* stream, const char \* format, va\_list ap); 函数说明：vfscanf()会自参数stream 的文件流中读取字符串, 再根据参数format 字符串来转换并格式化数据。格式转换形式请参考scanf(). 转换

](https://blog.csdn.net/Michaelwubo/article/details/41444929)

[

C语言_源码_学习第一天：学习string文件夹下的_源码_。

](https://blog.csdn.net/weixin_48985145/article/details/107165004)

[weixin\_48985145的博客](https://blog.csdn.net/weixin_48985145)

07-06 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 155 

[

下载_源码_。 首先，我们得下载C语言_源码_，其实在我们使用的一些编译器中也有C语言_源码_。 C语言_源码_下载网站 我这里选择的是画圈的部分，如果有其它的下载网站也可以使用。 第一节：学习string文件夹下的函数功能实现。 bzero.cpp void \_\_bzero (void \*s, size\_t len) { memset (s, '\\0', len); } weak\_alias (\_\_bzero, bzero) 可以看出，bzero函数文件下函数是是封装了memset，那么我们接下来看memset。

](https://blog.csdn.net/weixin_48985145/article/details/107165004)

[

_glibc__源码_分析之普通文件读写

](https://blog.csdn.net/pk_20140716/article/details/77386126)

[pk\_20140716的专栏](https://blog.csdn.net/pk_20140716)

08-18 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 1636 

[

_glibc_中关于普通文件读写的函数有open,close,read,write,lseek,lseek64。它们分别封装了open,close,read,write,lseek,\_llseek系统调用。 lseek用于在32位长度的文件中跳转，\_llseek用于在64位长度的文件中跳转。 open函数的封装在前文中已经介绍了。close函数定义在sysdeps/unix/sysv/linux/c

](https://blog.csdn.net/pk_20140716/article/details/77386126)

[

atof、atoi、atol、atoll

](https://rtoax.blog.csdn.net/article/details/86696805)

[RToax](https://blog.csdn.net/Rong_Toa)

01-29 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 599 

[

atoi.c    stdlib    964    2018/8/1    3 /\* Convert a string to a double. \*/ double atof (const char \*nptr) { return strtod (nptr, (char \*\*) NULL); } /\* Convert a string to an int. \*/ int atoi ...

](https://rtoax.blog.csdn.net/article/details/86696805)

[

linux下的系统调用函数到内核函数的追踪

](https://blog.csdn.net/missingu1314/article/details/8992465)

[missingu1314的专栏](https://blog.csdn.net/missingu1314)

05-30 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
 956 

[

转自：http://blog.chinaunix.net/uid-28458801-id-3468966.html 非常感谢！ 使用的 _glibc_ : _glibc_\-2.17 使用的 linux kernel ：linux-3.2.07   系统调用是内核向用户进程提供服务的唯一方法，应用程序调用操作系统提供的功能模块（函数）。 用户程序通过系统调

](https://blog.csdn.net/missingu1314/article/details/8992465)

### “相关推荐”对你有帮助么？

*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel1.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey1.png)
    
    非常没帮助
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel2.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey2.png)
    
    没帮助
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel3.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey3.png)
    
    一般
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel4.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey4.png)
    
    有帮助
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel5.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey5.png)
    
    非常有帮助
    

 提交

©️2022 CSDN 皮肤主题：深蓝海洋 设计师：CSDN官方博客 [返回首页](https://blog.csdn.net/)

*   [关于我们](//www.csdn.net/company/index.html#about)
*   [招贤纳士](//www.csdn.net/company/index.html#recruit)
*   [商务合作](//marketing.csdn.net/questions/Q2202181741262323995)
*   [寻求报道](//marketing.csdn.net/questions/Q2202181748074189855)
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/tel.png)
     400-660-0108
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/email.png)
     [kefu@csdn.net](mailto:webmaster@csdn.net)
*   ![](https://g.csdnimg.cn/common/csdn-footer/images/cs.png)
     [在线客服](https://csdn.s2.udesk.cn/im_client/?web_plugin_id=29181)
*   工作时间 8:30-22:00

*   ![](https://g.csdnimg.cn/common/csdn-footer/images/badge.png)
    [公安备案号11010502030143](http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=11010502030143)
*   [京ICP备19004658号](http://beian.miit.gov.cn/publish/query/indexFirst.action)
*   [京网文〔2020〕1039-165号](https://csdnimg.cn/release/live_fe/culture_license.png)
*   [经营性网站备案信息](https://csdnimg.cn/cdn/content-toolbar/csdn-ICP.png)
*   [北京互联网违法和不良信息举报中心](http://www.bjjubao.org/)
*   [家长监护](https://download.csdn.net/tutelage/home)
*   [网络110报警服务](http://www.cyberpolice.cn/)
*   [中国互联网举报中心](http://www.12377.cn/)
*   [Chrome商店下载](https://chrome.google.com/webstore/detail/csdn%E5%BC%80%E5%8F%91%E8%80%85%E5%8A%A9%E6%89%8B/kfkdboecolemdjodhmhmcibjocfopejo?hl=zh-CN)
*   [账号管理规范](https://blog.csdn.net/blogdevteam/article/details/126135357)
*   [版权与免责声明](https://www.csdn.net/company/index.html#statement)
*   [版权申诉](https://blog.csdn.net/blogdevteam/article/details/90369522)
*   [出版物许可证](https://img-home.csdnimg.cn/images/20220705052819.png)
*   [营业执照](https://img-home.csdnimg.cn/images/20210414021142.jpg)
*   ©1999-2022北京创新乐知网络技术有限公司

 [![](https://profile.csdnimg.cn/B/6/C/3_qq_29173507)](https://blog.csdn.net/qq_29173507) 

[能别闹](https://blog.csdn.net/qq_29173507 "能别闹") CSDN认证博客专家 CSDN认证企业博客

码龄7年 [![](https://csdnimg.cn/identity/nocErtification.png)
 暂无认证](https://i.csdn.net/#/uc/profile?utm_source=14998968 "暂无认证") 

[

21

原创

](https://blog.csdn.net/qq_29173507)

[

17万+

周排名

](https://blog.csdn.net/rank/list/weekly)

[

152万+

总排名

](https://blog.csdn.net/rank/list/total)

3万+

访问

 [![](https://csdnimg.cn/identity/blog2.png)](https://blog.csdn.net/blogdevteam/article/details/103478461) 

等级

326

积分

16

粉丝

22

获赞

9

评论

77

收藏

![](https://csdnimg.cn/medal/qiandao1@240.png)

![](https://csdnimg.cn/medal/chizhiyiheng@240.png)

![](https://csdnimg.cn/medal/qixiebiaobing4@240.png)

![](https://csdnimg.cn/medal/yuedu30@240.png)

[私信](https://im.csdn.net/chat/qq_29173507)

关注

 ![](https://csdnimg.cn/cdn/content-toolbar/csdn-sou.png?v=1587021042) 

### 热门文章

*   [vscode插件的使用highlight-words ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     7506](https://blog.csdn.net/qq_29173507/article/details/111570867) 
*   [iphone6 修改版本&&iccid解锁 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     5217](https://blog.csdn.net/qq_29173507/article/details/104881386) 
*   [c语言程序的编译过程 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     5102](https://blog.csdn.net/qq_29173507/article/details/113533622) 
*   [小米空气净化器2S换pm2.5传感器风扇 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     4602](https://blog.csdn.net/qq_29173507/article/details/111466293) 
*   [C语言关键字\_record ![](https://csdnimg.cn/release/blogv2/dist/pc/img/readCountWhite.png)
     1797](https://blog.csdn.net/qq_29173507/article/details/113745319) 

### 分类专栏

*    [![](https://img-blog.csdnimg.cn/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      工具](https://blog.csdn.net/qq_29173507/category_10684806.html) 1篇
*    [![](https://img-blog.csdnimg.cn/20201014180756925.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      面试归纳总结](https://blog.csdn.net/qq_29173507/category_11221744.html) 1篇
*    [![](https://img-blog.csdnimg.cn/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      linux](https://blog.csdn.net/qq_29173507/category_9819907.html) 3篇
*    [![](https://img-blog.csdnimg.cn/20201014180756927.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      C语言](https://blog.csdn.net/qq_29173507/category_9816363.html) 15篇
*    [![](https://img-blog.csdnimg.cn/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      搞机玩](https://blog.csdn.net/qq_29173507/category_9807329.html) 2篇
*    [![](https://img-blog.csdnimg.cn/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      for myself](https://blog.csdn.net/qq_29173507/category_9440629.html) 

![](https://csdnimg.cn/release/blogv2/dist/pc/img/arrowDownWhite.png)

### 最新评论

*   [vscode插件的使用highlight-words](https://blog.csdn.net/qq_29173507/article/details/111570867#comments_23877264)
    
    [qq\_42106292:](https://blog.csdn.net/qq_42106292) 用第二种方法修改不起作用，已验证，但是可以在插件扩展设置中修改
    
*   [c语言程序的编译过程](https://blog.csdn.net/qq_29173507/article/details/113533622#comments_21295467)
    
    [Kathryn7:](https://blog.csdn.net/qq_61551948) 谢谢很详细！
    
*   [vscode插件的使用highlight-words](https://blog.csdn.net/qq_29173507/article/details/111570867#comments_19881526)
    
    [何不当头给他一棒:](https://blog.csdn.net/Kaniiie) 最后那个配置真的有毒，多谢老哥，终于找到问题所在了。
    
*   [glibc源码-libc\_hidden\_def](https://blog.csdn.net/qq_29173507/article/details/112324568#comments_17236199)
    
    [远远看看山:](https://blog.csdn.net/u010330109) 优秀，心血来潮研究这个也遇到了困惑，博主厉害
    
*   [小米空气净化器2S换pm2.5传感器风扇](https://blog.csdn.net/qq_29173507/article/details/111466293#comments_15208699)
    
    [爱数据采集的大宝:](https://blog.csdn.net/m0_54538166) 我买了几个传感器，用串口助手测试PM2.5，确实很好玩。省的买商品啦！![](https://g.csdnimg.cn/static/face/monkey2/002.png)
    

### 您愿意向朋友推荐“博客详情页”吗？

*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel1.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey1.png)
    
    强烈不推荐
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel2.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey2.png)
    
    不推荐
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel3.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey3.png)
    
    一般般
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel4.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey4.png)
    
    推荐
    
*   ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeel5.png)
     ![](https://csdnimg.cn/release/blogv2/dist/pc/img/npsFeelGrey5.png)
    
    强烈推荐
    

 提交

### 最新文章

*   [面试题record](https://blog.csdn.net/qq_29173507/article/details/118930312)
*   [程序员的自我修养--看书总结(更新ing)](https://blog.csdn.net/qq_29173507/article/details/118734833)
*   [gcc -D选项 宏定义](https://blog.csdn.net/qq_29173507/article/details/113770163)

[2021年13篇](https://blog.csdn.net/qq_29173507?type=blog&year=2021&month=07)

[2020年8篇](https://blog.csdn.net/qq_29173507?type=blog&year=2020&month=12)

![](https://kunyu.csdn.net/1.png?p=57&adId=1015194&a=1015194&c=0&k=glibc源码-libc_hidden_def&spm=1001.2101.3001.5001&articleId=112324568&d=1&t=3&u=28765dde086145b0963a168052c167ff)

### 目录

1.  [ldbl\_hidden\_def (\_\_\_vfscanf, \_\_vfscanf)](#t0)
2.  [libc\_hidden\_def的作用](#t1)
3.  [libc\_hidden\_def的实现](#t2)

![](https://kunyu.csdn.net/1.png?p=530&adId=1015191&a=1015191&c=0&k=glibc源码-libc_hidden_def&spm=1001.2101.3001.4647&articleId=112324568&d=1&t=3&u=86f16e5b88e64c51980bba3cd9685c27)

### 目录

1.  [ldbl\_hidden\_def (\_\_\_vfscanf, \_\_vfscanf)](#t0)
2.  [libc\_hidden\_def的作用](#t1)
3.  [libc\_hidden\_def的实现](#t2)

![](https://kunyu.csdn.net/1.png?p=479&adId=1015221&a=1015221&c=0&k=glibc源码-libc_hidden_def&spm=1001.2101.3001.4834&articleId=112324568&d=1&t=3&u=4e0c15c5854b4d58b30f754131036d1d)

### 分类专栏

*    [![](https://img-blog.csdnimg.cn/20201014180756918.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      工具](https://blog.csdn.net/qq_29173507/category_10684806.html) 1篇
*    [![](https://img-blog.csdnimg.cn/20201014180756925.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      面试归纳总结](https://blog.csdn.net/qq_29173507/category_11221744.html) 1篇
*    [![](https://img-blog.csdnimg.cn/20201014180756930.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      linux](https://blog.csdn.net/qq_29173507/category_9819907.html) 3篇
*    [![](https://img-blog.csdnimg.cn/20201014180756927.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      C语言](https://blog.csdn.net/qq_29173507/category_9816363.html) 15篇
*    [![](https://img-blog.csdnimg.cn/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      搞机玩](https://blog.csdn.net/qq_29173507/category_9807329.html) 2篇
*    [![](https://img-blog.csdnimg.cn/20201014180756928.png?x-oss-process=image/resize,m_fixed,h_64,w_64)
      for myself](https://blog.csdn.net/qq_29173507/category_9440629.html) 

### 目录

1.  [ldbl\_hidden\_def (\_\_\_vfscanf, \_\_vfscanf)](#t0)
2.  [libc\_hidden\_def的作用](#t1)
3.  [libc\_hidden\_def的实现](#t2)

评论 1

![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

 [![](https://profile.csdnimg.cn/9/A/2/3_qq_26713443)](https://blog.csdn.net/qq_26713443) 

还能输入_1000_个字符

![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentEmotionIcon.png)
 插入表情

![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentCodeIcon.png)
 代码片

*   HTML/XML
*   objective-c
*   Ruby
*   PHP
*   C
*   C++
*   JavaScript
*   Python
*   Java
*   CSS
*   SQL
*   其它

     

*   [![](https://profile.csdnimg.cn/6/A/B/3_u010330109)
    ](https://blog.csdn.net/u010330109)
    
    [远远看看山](https://blog.csdn.net/u010330109) 2021.06.28
    
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentLookMore.png)
    
    举报
    
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newCommentReplyWhite.png)
    回复
    
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentLikeWhite.png)
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentLikeHover.png)
    ![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentLikeActive.png)
    
    优秀，心血来潮研究这个也遇到了困惑，博主厉害
    

查看更多评论![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowDownWhite.png)

0 条评论被折叠 查看

![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowLeftWhite.png)
被折叠的 0 条评论 [为什么被折叠?](https://blogdev.blog.csdn.net/article/details/122245662) [ ![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconPark.png)
到【灌水乐园】发言](https://bbs.csdn.net/forums/FreeZone)

查看更多评论![](https://csdnimg.cn/release/blogv2/dist/pc/img/commentArrowDownWhite.png)

打赏作者![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

 [![](https://profile.csdnimg.cn/B/6/C/3_qq_29173507)](https://blog.csdn.net/qq_29173507) 

能别闹

你的鼓励将是我创作的最大动力

¥2 ¥4 ¥6 ¥10 ¥20 

输入1-500的整数

![](https://csdnimg.cn/release/blogv2/dist/pc/img/newUnChoose.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newChoose.png)
 余额支付 (余额：-- )

![](https://csdnimg.cn/release/blogv2/dist/pc/img/newUnChoose.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newChoose.png)
 扫码支付

扫码支付：¥2

![](https://csdnimg.cn/release/blogv2/dist/pc/img/pay-time-out.png)
 获取中

![](https://csdnimg.cn/release/blogv2/dist/pc/img/newWeiXin.png)
 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/newZhiFuBao.png)
 扫码支付

您的余额不足，请更换扫码支付或[充值](https://i.csdn.net/#/wallet/balance/recharge?utm_source=RewardVip)

打赏作者

实付元

[使用余额支付](javascript:;)

![](https://csdnimg.cn/release/blogv2/dist/pc/img/pay-time-out.png)
 点击重新获取

![](https://csdnimg.cn/release/blogv2/dist/pc/img/weixin.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/zhifubao.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/jingdong.png)
扫码支付

 钱包余额 0

![](https://csdnimg.cn/release/blogv2/dist/pc/img/pay-help.png)

抵扣说明：

1.余额是钱包充值的虚拟货币，按照1:1的比例进行支付金额的抵扣。  
2.余额无法直接购买下载，可以购买VIP、C币套餐、付费专栏及课程。

[![](https://csdnimg.cn/release/blogv2/dist/pc/img/recharge.png)
余额充值](https://i.csdn.net/#/wallet/balance/recharge)

确定取消![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBt.png)

举报

![](https://csdnimg.cn/release/blogv2/dist/pc/img/closeBlack.png)

选择你想要举报的内容（必选）

*   内容涉黄
*   政治相关
*   内容抄袭
*   涉嫌广告
*   内容侵权
*   侮辱谩骂
*   样式问题
*   其他

原文链接（必填）

请选择具体原因（必选）

*   包含不实信息
*   涉及个人隐私

请选择具体原因（必选）

*   侮辱谩骂
*   诽谤

请选择具体原因（必选）

*   搬家样式
*   博文样式

补充说明（选填）

取消

确定

 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconShowDirectory.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconSideBeta.png)
 只看  
目录![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconHideDirectory.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconSideBeta.png)
 隐藏  
目录 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconShowSide.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconSideBeta.png)
 显示  
侧栏 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconHideSide.png)
![](https://csdnimg.cn/release/blogv2/dist/pc/img/iconSideBeta.png)
 隐藏  
侧栏 ![](https://g.csdnimg.cn/side-toolbar/3.4/images/guide.png)
 新手  
引导 ![](https://g.csdnimg.cn/side-toolbar/3.4/images/kefu.png)
 客服   举报   ![](https://g.csdnimg.cn/side-toolbar/3.4/images/fanhuidingbucopy.png)
 返回  
顶部