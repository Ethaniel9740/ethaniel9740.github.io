---
title: hexo + Butterfly + busuanzi无法统计访客量
date: 2025-12-05 17:23:00
updated: 2025-12-05 17:23:00
categories: 'hexo'
copyright_author: Ethaniel
---

### 问题描述

在使用 Hexo 搭建博客时，在博客中集成了站点访问数据量统计插件 [busuanzi](http://busuanzi.ibruce.info/)。在本地启动服务后，统计数据无法加载。

![hexo2_1](img\hexo2_1.png)

问题分析
静态网站是无后台服务支撑的，大多数情况下都需要借助第三方的插件实现相关功能。

具体的原因博主也没有弄清楚。猜测是在本地部署时，未检测到busuanzi插件，或是博客主题（butterfly）中安装新的插件导致无法检测busuanzi插件


### 解决方法

修改主体下的D:\blog\butt\node_modules\hexo-theme-butterfly\ _config.yml（我的目录：D:\blog\butt\ _config.butterfly.yml，可以将主题下的配置文件复制粘贴到根目录下改名为 _config.butterfly.yml），搜索inject，新增如下参数：

```yaml
- <script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

![hexo2_2](img\hexo2_2.png)

### 预览效果

开启本地server

```nginx
hexo c && hexo g && hexo s
```

访问：http://localhost:4000/ ，即可看到想要的统计功能了

![hexo2_3](img\hexo2_3.png)
