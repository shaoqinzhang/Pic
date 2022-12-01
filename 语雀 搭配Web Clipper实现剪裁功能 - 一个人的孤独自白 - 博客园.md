# 语雀 搭配Web Clipper实现剪裁功能 - 一个人的孤独自白 - 博客园
        语雀 搭配Web Clipper实现剪裁功能 - 一个人的孤独自白 - 博客园           

*    [![](https://common.cnblogs.com/logo.svg)](https://www.cnblogs.com/ "开发者的网上家园") 
*   [首页](/)
*   [新闻](https://news.cnblogs.com/)
*   [博问](https://q.cnblogs.com/)
*   [专区](https://brands.cnblogs.com/)
*   [闪存](https://ing.cnblogs.com/)
*   [班级](https://edu.cnblogs.com/)

*    ![](https://common.cnblogs.com/images/blog/search.svg) 
    
*    [![](https://common.cnblogs.com/images/blog/newpost.svg)](https://i.cnblogs.com/EditPosts.aspx?opt=1 "写随笔") [ ![](https://common.cnblogs.com/images/blog/myblog.svg)
     ](https://passport.cnblogs.com/GetBlogApplyStatus.aspx "我的博客") [ ![](https://common.cnblogs.com/images/blog/message.svg)
      ](https://msg.cnblogs.com/ "短消息") [![](https://common.cnblogs.com/images/blog/lite-mode-on.svg)](javascript:void(0) "简洁模式启用，您在访问他人博客时会使用简洁款皮肤展示") 
    
     [![](https://common.cnblogs.com/images/blog/avatar-default.svg)](https://home.cnblogs.com/) 
    
    [我的博客](https://passport.cnblogs.com/GetBlogApplyStatus.aspx) [我的园子](https://home.cnblogs.com/) [账号设置](https://account.cnblogs.com/settings/account) [简洁模式 ![](https://www.cnblogs.com/images/lite-mode-check.svg)
    ... ](javascript:void(0) "简洁模式会使用简洁款皮肤显示所有博客") [退出登录](javascript:void(0))
    
    [注册](https://account.cnblogs.com/signup) [登录](javascript:void(0);)

[一个人的孤独自白](https://www.cnblogs.com/-mrl/)

*   [博客园](https://www.cnblogs.com/)
*   [首页](https://www.cnblogs.com/-mrl/)
*   [新随笔](https://i.cnblogs.com/EditPosts.aspx?opt=1)
*   [联系](https://msg.cnblogs.com/send/%E4%B8%80%E4%B8%AA%E4%BA%BA%E7%9A%84%E5%AD%A4%E7%8B%AC%E8%87%AA%E7%99%BD)
*   [订阅](javascript:void(0))
*   [管理](https://i.cnblogs.com/)

随笔 - 595  文章 - 0  评论 - 47  阅读 - 137万

[语雀 搭配Web Clipper实现剪裁功能](https://www.cnblogs.com/-mrl/p/14335403.html)
======================================================================

 语雀官网：

 [https://www.yuque.com/login?platform=wechat&inviteToken=357df65e3061673e3b03a080fade2e49a13f671ae1cf56d90bd2419632226e3f](https://www.yuque.com/login?platform=wechat&inviteToken=357df65e3061673e3b03a080fade2e49a13f671ae1cf56d90bd2419632226e3f)

![](https://img2020.cnblogs.com/blog/867078/202101/867078-20210127160059896-1195947864.png)

语雀Web Clipper剪藏：

这是一个可以将你在浏览器上看到的内容保存到语雀的功能，类似于印象笔记的网页剪藏功能。

使用语雀剪藏之前，你需要先为你的浏览器安装一个 插件—— Web Clipper。

Web Clipper是一个聚合类的笔记剪藏插件，可以绑定不同平台的账号，如Bear、OneNote和语雀等。

Web Clipper下载地址：

官网：[https://clipper.website/](https://clipper.website/)

github：[https://github.com/webclipper/web-clipper](https://github.com/webclipper/web-clipper)

web\_clipper\_chrome.zip：[https://github.com/webclipper/web-clipper/releases](https://github.com/webclipper/web-clipper/releases)

插件使用截图
------

![](https://img-blog.csdnimg.cn/20190924132819608.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)
  
![](https://img-blog.csdnimg.cn/20190924133028539.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)
  
![](https://img-blog.csdnimg.cn/20190924132840810.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)
  
![](https://img-blog.csdnimg.cn/20190924133036372.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)
  
![](https://img-blog.csdnimg.cn/20190924133109688.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)
  
![](https://img-blog.csdnimg.cn/20190924133154929.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2JlbmRhbmJhaWNoaTE5ODk=,size_16,color_FFFFFF,t_70)

[好文要顶](javascript:void(0);) [关注我](javascript:void(0);) [收藏该文](javascript:void(0);) [![](https://common.cnblogs.com/images/icon_weibo_24.png)
](javascript:void(0); "分享至新浪微博") [![](https://common.cnblogs.com/images/wechat.png)
](javascript:void(0); "分享至微信")

[![](https://pic.cnblogs.com/face/sample_face.gif)
](https://home.cnblogs.com/u/-mrl/)

[一个人的孤独自白](https://home.cnblogs.com/u/-mrl/)  
[粉丝 - 39](https://home.cnblogs.com/u/-mrl/followers/) [关注 - 6](https://home.cnblogs.com/u/-mrl/followees/)  

[+加关注](javascript:void(0);)

0

0

[«](https://www.cnblogs.com/-mrl/p/14317011.html) 上一篇： [mongodb 集合新增字段、删除字段、修改字段](https://www.cnblogs.com/-mrl/p/14317011.html "发布于 2021-01-23 11:29")  
[»](https://www.cnblogs.com/-mrl/p/14345572.html) 下一篇： [sourceTree 配置外部比较工具BeyondCompare 解决冲突](https://www.cnblogs.com/-mrl/p/14345572.html "发布于 2021-01-29 16:15")

posted @ 2021-01-27 15:56  [一个人的孤独自白](https://www.cnblogs.com/-mrl/)  阅读(3612)  评论(0)  [编辑](https://i.cnblogs.com/EditPosts.aspx?postid=14335403)  [收藏](javascript:void(0))  [举报](javascript:void(0))

[刷新评论](javascript:void(0);)[刷新页面](#)[返回顶部](#top)

登录后才能查看或发表评论，立即 [登录](javascript:void(0);) 或者 [逛逛](https://www.cnblogs.com/) 博客园首页

[【推荐】阿里云新人特惠，爆款云服务器2核4G低至0.46元/天](https://click.aliyun.com/m/1000365553/)  
[【推荐】双十一同价！腾讯云云服务器抢先购，低至4.2元/月](https://cloud.tencent.com/act/cps/redirect?redirect=2446&cps_key=6a15b90f1178f38fb09b07f16943cf3e&from=console)  

**编辑推荐：**   
· [谁说.NET没有GC调优？只改一行代码就让程序不再占用内存](https://www.cnblogs.com/rupeng/p/16937307.html)  
· [为什么标准库的模板变量都是 inline 的](https://www.cnblogs.com/apocelipes/p/16931410.html)  
· [.net 如何优雅的使用 EFCore](https://www.cnblogs.com/qwqwQAQ/p/16932139.html)  
· [在 C# 中使用 Halcon 开发视觉检测程序](https://www.cnblogs.com/timefiles/p/16928651.html)  
· [聊一聊如何截获 C# 程序产生的日志](https://www.cnblogs.com/huangxincheng/p/16924078.html)  

**阅读排行：**   
· [谁说.NET没有GC调优？只改一行代码就让程序不再占用内存](https://www.cnblogs.com/rupeng/p/16937307.html)  
· [文件服务器 — File Browser](https://www.cnblogs.com/zhurong/p/16937645.html)  
· [初次邂逅 EasyExcel](https://www.cnblogs.com/god23bin/p/easy-excel-use.html)  
· [Entity Framework Core 7中高效地进行批量数据插入](https://www.cnblogs.com/rupeng/p/16940576.html)  
· [快速绘制流程图「GitHub 热点速览 v.22.47」](https://www.cnblogs.com/xueweihan/p/16940364.html)  

**历史上的今天：**   
2016-01-27 [百度地图API地点搜索-获取经纬度](https://www.cnblogs.com/-mrl/p/5162571.html)  

### 公告

昵称： [一个人的孤独自白](https://home.cnblogs.com/u/-mrl/)  
园龄： [6年11个月](https://home.cnblogs.com/u/-mrl/ "入园时间：2015-12-27")  
粉丝： [39](https://home.cnblogs.com/u/-mrl/followers/)  
关注： [6](https://home.cnblogs.com/u/-mrl/followees/)

[+加关注](javascript:void(0))

| 
| [<](javascript:void(0);) | 2022年12月 | [\>](javascript:void(0);) | |
| 日 | 一 | 二 | 三 | 四 | 五 | 六 |
| 27 | 28 | 29 | 30 | 1 | 2 | 3 |
| 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| 11 | 12 | 13 | 14 | 15 | 16 | 17 |
| 18 | 19 | 20 | 21 | 22 | 23 | 24 |
| 25 | 26 | 27 | 28 | 29 | 30 | 31 |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 |

### 搜索

 

 

### 常用链接

*   [我的随笔](https://www.cnblogs.com/-mrl/p/ "我的博客的随笔列表")
*   [我的评论](https://www.cnblogs.com/-mrl/MyComments.html "我的发表过的评论列表")
*   [我的参与](https://www.cnblogs.com/-mrl/OtherPosts.html "我评论过的随笔列表")
*   [最新评论](https://www.cnblogs.com/-mrl/comments "我的博客的评论列表")
*   [我的标签](https://www.cnblogs.com/-mrl/tag/ "我的博客的标签列表")

### [随笔分类](https://www.cnblogs.com/-mrl/categories)

*   [docker/docker-compose(20)](https://www.cnblogs.com/-mrl/category/1803992.html)
*   [elasticsearch/es(14)](https://www.cnblogs.com/-mrl/category/1868348.html)
*   [git/sourcetree(31)](https://www.cnblogs.com/-mrl/category/1867468.html)
*   [html/js/jquery(30)](https://www.cnblogs.com/-mrl/category/1191790.html)
*   [laravel(2)](https://www.cnblogs.com/-mrl/category/2127252.html)
*   [linux\[centos/ubuntu \](67)](https://www.cnblogs.com/-mrl/category/771882.html)
*   [PHP&mysql(245)](https://www.cnblogs.com/-mrl/category/771894.html)
*   [phpstorm(13)](https://www.cnblogs.com/-mrl/category/1876966.html)
*   [python(7)](https://www.cnblogs.com/-mrl/category/1630301.html)
*   [rabbitmq(16)](https://www.cnblogs.com/-mrl/category/1492071.html)
*   [redis(9)](https://www.cnblogs.com/-mrl/category/1798689.html)
*   [Thinkphp(1)](https://www.cnblogs.com/-mrl/category/802802.html)
*   [vagrant/virtualBox(6)](https://www.cnblogs.com/-mrl/category/1876964.html)
*   [Yii2.0(17)](https://www.cnblogs.com/-mrl/category/906479.html)
*   [其他(59)](https://www.cnblogs.com/-mrl/category/771891.html)
*   [未鉴定(转载)(6)](https://www.cnblogs.com/-mrl/category/772249.html)
*   [小程序(2)](https://www.cnblogs.com/-mrl/category/1223477.html)

### 随笔档案

*   [2022年11月(2)](https://www.cnblogs.com/-mrl/archive/2022/11.html)
*   [2022年9月(1)](https://www.cnblogs.com/-mrl/archive/2022/09.html)
*   [2022年6月(1)](https://www.cnblogs.com/-mrl/archive/2022/06.html)
*   [2022年5月(4)](https://www.cnblogs.com/-mrl/archive/2022/05.html)
*   [2022年4月(1)](https://www.cnblogs.com/-mrl/archive/2022/04.html)
*   [2022年3月(2)](https://www.cnblogs.com/-mrl/archive/2022/03.html)
*   [2022年1月(4)](https://www.cnblogs.com/-mrl/archive/2022/01.html)
*   [2021年12月(3)](https://www.cnblogs.com/-mrl/archive/2021/12.html)
*   [2021年11月(5)](https://www.cnblogs.com/-mrl/archive/2021/11.html)
*   [2021年10月(1)](https://www.cnblogs.com/-mrl/archive/2021/10.html)
*   [2021年9月(3)](https://www.cnblogs.com/-mrl/archive/2021/09.html)
*   [2021年8月(1)](https://www.cnblogs.com/-mrl/archive/2021/08.html)
*   [2021年7月(4)](https://www.cnblogs.com/-mrl/archive/2021/07.html)
*   [2021年5月(4)](https://www.cnblogs.com/-mrl/archive/2021/05.html)
*   [2021年4月(5)](https://www.cnblogs.com/-mrl/archive/2021/04.html)
*   [2021年3月(1)](https://www.cnblogs.com/-mrl/archive/2021/03.html)
*   [2021年2月(1)](https://www.cnblogs.com/-mrl/archive/2021/02.html)
*   [2021年1月(10)](https://www.cnblogs.com/-mrl/archive/2021/01.html)
*   [2020年12月(7)](https://www.cnblogs.com/-mrl/archive/2020/12.html)
*   [2020年11月(15)](https://www.cnblogs.com/-mrl/archive/2020/11.html)
*   [2020年10月(34)](https://www.cnblogs.com/-mrl/archive/2020/10.html)
*   [2020年9月(13)](https://www.cnblogs.com/-mrl/archive/2020/09.html)
*   [2020年8月(17)](https://www.cnblogs.com/-mrl/archive/2020/08.html)
*   [2020年7月(52)](https://www.cnblogs.com/-mrl/archive/2020/07.html)
*   [2020年6月(24)](https://www.cnblogs.com/-mrl/archive/2020/06.html)
*   [2020年5月(1)](https://www.cnblogs.com/-mrl/archive/2020/05.html)
*   [2020年2月(1)](https://www.cnblogs.com/-mrl/archive/2020/02.html)
*   [2020年1月(28)](https://www.cnblogs.com/-mrl/archive/2020/01.html)
*   [2019年12月(10)](https://www.cnblogs.com/-mrl/archive/2019/12.html)
*   [2019年11月(12)](https://www.cnblogs.com/-mrl/archive/2019/11.html)
*   [2019年10月(5)](https://www.cnblogs.com/-mrl/archive/2019/10.html)
*   [2019年9月(8)](https://www.cnblogs.com/-mrl/archive/2019/09.html)
*   [2019年8月(9)](https://www.cnblogs.com/-mrl/archive/2019/08.html)
*   [2019年7月(21)](https://www.cnblogs.com/-mrl/archive/2019/07.html)
*   [2019年6月(20)](https://www.cnblogs.com/-mrl/archive/2019/06.html)
*   [2019年5月(10)](https://www.cnblogs.com/-mrl/archive/2019/05.html)
*   [2019年4月(20)](https://www.cnblogs.com/-mrl/archive/2019/04.html)
*   [2019年3月(9)](https://www.cnblogs.com/-mrl/archive/2019/03.html)
*   [2019年2月(4)](https://www.cnblogs.com/-mrl/archive/2019/02.html)
*   [2019年1月(3)](https://www.cnblogs.com/-mrl/archive/2019/01.html)
*   [2018年12月(10)](https://www.cnblogs.com/-mrl/archive/2018/12.html)
*   [2018年11月(7)](https://www.cnblogs.com/-mrl/archive/2018/11.html)
*   [2018年10月(9)](https://www.cnblogs.com/-mrl/archive/2018/10.html)
*   [2018年9月(8)](https://www.cnblogs.com/-mrl/archive/2018/09.html)
*   [2018年8月(4)](https://www.cnblogs.com/-mrl/archive/2018/08.html)
*   [2018年7月(3)](https://www.cnblogs.com/-mrl/archive/2018/07.html)
*   [2018年6月(9)](https://www.cnblogs.com/-mrl/archive/2018/06.html)
*   [2018年5月(15)](https://www.cnblogs.com/-mrl/archive/2018/05.html)
*   [2018年4月(19)](https://www.cnblogs.com/-mrl/archive/2018/04.html)
*   [2018年3月(7)](https://www.cnblogs.com/-mrl/archive/2018/03.html)
*   [2018年2月(1)](https://www.cnblogs.com/-mrl/archive/2018/02.html)
*   [2018年1月(7)](https://www.cnblogs.com/-mrl/archive/2018/01.html)
*   [2017年12月(3)](https://www.cnblogs.com/-mrl/archive/2017/12.html)
*   [2017年11月(7)](https://www.cnblogs.com/-mrl/archive/2017/11.html)
*   [2017年10月(10)](https://www.cnblogs.com/-mrl/archive/2017/10.html)
*   [2017年9月(13)](https://www.cnblogs.com/-mrl/archive/2017/09.html)
*   [2017年7月(16)](https://www.cnblogs.com/-mrl/archive/2017/07.html)
*   [2017年6月(1)](https://www.cnblogs.com/-mrl/archive/2017/06.html)
*   [2017年5月(3)](https://www.cnblogs.com/-mrl/archive/2017/05.html)
*   [2017年4月(2)](https://www.cnblogs.com/-mrl/archive/2017/04.html)
*   [2017年3月(2)](https://www.cnblogs.com/-mrl/archive/2017/03.html)
*   [2017年2月(3)](https://www.cnblogs.com/-mrl/archive/2017/02.html)
*   [2017年1月(4)](https://www.cnblogs.com/-mrl/archive/2017/01.html)
*   [2016年11月(8)](https://www.cnblogs.com/-mrl/archive/2016/11.html)
*   [2016年10月(4)](https://www.cnblogs.com/-mrl/archive/2016/10.html)
*   [2016年9月(2)](https://www.cnblogs.com/-mrl/archive/2016/09.html)
*   [2016年8月(1)](https://www.cnblogs.com/-mrl/archive/2016/08.html)
*   [2016年7月(5)](https://www.cnblogs.com/-mrl/archive/2016/07.html)
*   [2016年6月(1)](https://www.cnblogs.com/-mrl/archive/2016/06.html)
*   [2016年5月(8)](https://www.cnblogs.com/-mrl/archive/2016/05.html)
*   [2016年4月(2)](https://www.cnblogs.com/-mrl/archive/2016/04.html)
*   [2016年3月(4)](https://www.cnblogs.com/-mrl/archive/2016/03.html)
*   [2016年1月(12)](https://www.cnblogs.com/-mrl/archive/2016/01.html)
*   [2015年12月(9)](https://www.cnblogs.com/-mrl/archive/2015/12.html)
*   [更多](javascript:void(0))

### [阅读排行榜](https://www.cnblogs.com/-mrl/most-viewed)

*   [1\. win10 配置git 环境变量(54165)](https://www.cnblogs.com/-mrl/p/11246666.html)
*   [2\. mysql误删数据快速恢复(46230)](https://www.cnblogs.com/-mrl/p/9959365.html)
*   [3\. Linux（Centos7）下搭建svn服务器(43872)](https://www.cnblogs.com/-mrl/p/8980244.html)
*   [4\. postman跳过登陆直接使用的办法(36037)](https://www.cnblogs.com/-mrl/p/11578619.html)
*   [5\. phpStudy环境配置多个站点，绑定域名(25736)](https://www.cnblogs.com/-mrl/p/5386112.html)

### [评论排行榜](https://www.cnblogs.com/-mrl/most-commented)

*   [1\. Linux（Centos7）下搭建svn服务器(7)](https://www.cnblogs.com/-mrl/p/8980244.html)
*   [2\. php+redis，延迟任务 实现自动取消订单，自动完成订单(4)](https://www.cnblogs.com/-mrl/p/9519259.html)
*   [3\. JS自己实现字符串加密和解密算法(3)](https://www.cnblogs.com/-mrl/p/15251834.html)
*   [4\. 安卓 android studio 报错 Unknown host 'jcenter.bintray.com'. You may need to adjust the proxy settings in Gradle.(3)](https://www.cnblogs.com/-mrl/p/11130684.html)
*   [5\. mysql 事务的实现原理(2)](https://www.cnblogs.com/-mrl/p/13369209.html)

### [推荐排行榜](https://www.cnblogs.com/-mrl/most-liked)

*   [1\. Linux（Centos7）下搭建svn服务器(6)](https://www.cnblogs.com/-mrl/p/8980244.html)
*   [2\. mysql误删数据快速恢复(5)](https://www.cnblogs.com/-mrl/p/9959365.html)
*   [3\. MySQL实现排名并查询指定用户排名功能(4)](https://www.cnblogs.com/-mrl/p/9073375.html)
*   [4\. MYSQL | 最左匹配原则(3)](https://www.cnblogs.com/-mrl/p/13230006.html)
*   [5\. postman 测试Excel文件导入导出功能(3)](https://www.cnblogs.com/-mrl/p/11607828.html)

### [最新评论](https://www.cnblogs.com/-mrl/comments)

*   [1\. Re:MYSQL | 最左匹配原则](https://www.cnblogs.com/-mrl/p/13230006.html)
*   “值得注意的是，in 和 = 都可以乱序，比如有索引（a,b,c），语句 select \* from t where c =1 and a=1 and b=1，这样的语句也可以用到最左匹配，因为 My...
*   \--longbozhan
*   [2\. Re:JS自己实现字符串加密和解密算法](https://www.cnblogs.com/-mrl/p/15251834.html)
*   解码的eval这一段我换成new Funciton为啥不行呢。
    
*   \--#山鸡
*   [3\. Re:JS自己实现字符串加密和解密算法](https://www.cnblogs.com/-mrl/p/15251834.html)
*   不对，我把解码的eval去掉就解不了了
    
*   \--#山鸡
*   [4\. Re:JS自己实现字符串加密和解密算法](https://www.cnblogs.com/-mrl/p/15251834.html)
*   解密不出来
    
*   \--#山鸡
*   [5\. Re:ECS上nginx搭建反向代理通过内网访问阿里云OSS服务](https://www.cnblogs.com/-mrl/p/10691271.html)
*   /data/wwwroot/test/uploads/;是bucket路径吗
    
*   \--曦花

Copyright © 2022 一个人的孤独自白  
Powered by .NET 7.0 on Kubernetes