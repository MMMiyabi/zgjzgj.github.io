---
layout:     post
title:      "jekyll第三方评论系统"
subtitle:   ""
date:       2022-3-16 12:40:00
author:     "zgj"
catalog: true
header-style: text
tags: 网站建设
---

### Disqus

说到第三方评论系统首先就是Disqus。优点很多（我还没有来得及去感受），有几档价格可以选择，可以选择免费的，但是得看广告。

**使用**

Disqus的使用很简单，上官网https://disqus.com/照着来就行了。

### Talkyard

Talkyard是一款比Disqus更轻量的第三方评论系统，亮点是开源。你可以将它免费部署到自己的服务器上，也可以付费享受服务。

**使用**

在其开源的github网站上有详细的部署教程https://github.com/debiki/talkyard-prod-one

### HyperComments

> 来自俄罗斯的评论系统，使用谷歌账号注册。免费用户支持一个网站和一个管理员，对于个人博客来说足够用了。功能暂且不说，光看这清爽的界面，作为一只颜狗，我是服气的。

太卡了，进不去

### 来必力

> 来自韩国，使用邮箱注册。不得不承认颜值也很高，准确地说应该是萌。中国地区的本地化做得很不错，甚至可以用微信登陆留言，简直热泪盈眶。就这点来看，是多说最好的替代品。同时支持的登陆方式还有：新浪微博、QQ、百度、人人、豆瓣。顺带提一下在韩文和英文模式下的登陆方式：来必力、Kakao talk、Naver、Facebook、Twitter、Instagram、Line、GitHub、Tistory、Google+、Linkedin。

来必力的使用比较方便，但**修改评论框样式是收费项目。**

此外，本人在使用时还发现，来必力不会在你进入网页的时候预加载， 因此每次拖到评论区的时候等待加载的时候比较长。

**使用**

注册登录

在官网上选择安装

![](https://i.vgy.me/cTwSw9.png)

在_config.yml文件中添加来必力模块

`livere_uid:  MTAyMC81NTczNC8zMjIwMA==`

将安装代码添加到post.html中



![](https://i.vgy.me/FN8FVd.png)

成功

![](https://i.vgy.me/EpYM7j.png)

### IntenseDebate

> 是 WordPress 所在的 Automattic 旗下的产品。优点是支持游客评论。国内可以用，但听说加载略慢。曾经是 Disqus 强有力的对手。既然和 WordPress 同一东家，想必反垃圾邮件的功能应该做得不错。如果有 WordPress 账户就不需要额外注册，但很多用 WP 的都可以使用原生评论，这真是个奇妙的悖论。

加载比来必力快，但个人觉得界面没有来必力美观，且不如来必力贴近中国用户

![](https://i.vgy.me/miimI3.png)

**使用**

1. 先去IntenseDebate注册一个账号。

2. 在Jekyll站点的_includes目录下创建intensedebate-comments.html文件.

   文件内容如下。在{% if page.comments != false %}和{% endif %}之间就是IntenseDebate注册完以后得到的脚步代码

    {% if page.comments != false %}
        <script>
        var idcomments_acct = 'xxxx50b9b39';
        var idcomments_post_id = '{{ page.url }}';
        var idcomments_post_url;
        </script>
        <span id="IDCommentsPostTitle" style="display:none"></span>
        <script type='text/javascript' src='https://www.intensedebate.com/js/genericCommentWrapperV2.js'></script>
    {% endif %}
    ————————————————
    版权声明：本文为CSDN博主「moakap」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
    原文链接：https://blog.csdn.net/ljinddlj/article/details/52273652

3. 在站点配置文件中添加评论配置参数，方便灵活的enable/disable评论功能。

​     `intensedebate_comments: true`

4. 在post.html文件末尾后面添加代码引用intensedebate-comments.html来显示评论框	

    {% if site.intensedebate_comments %}
      {% include intensedebate-comments.html %}
    {% endif %}

### 畅言

> 搜狐旗下，大牌加持，安装需要备案号。界面还算清爽，不满意的话可以自定义样式。

要备案，致命伤

### Valine

据说很好用，但我试了一下没成功

### Vicomi

> 免费用户支持一个域名。特点是可以选择心情表情。也因此界面有些凌乱。
>
> Vicomi 是评论界的表情帝

表情这个功能很吸引我，但无奈没法注册