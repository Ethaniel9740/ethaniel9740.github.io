---
title: hexo + Butterfly本地搜索功能
date: 2025-12-05 16:37:00
updated: 2025-12-05 16:37:00
categories: 'hexo'
copyright_author: Ethaniel
---

### 安装依赖 

前往博客根目录，打开cmd命令窗口执行

```shell
npm install hexo-generator-search --save
```

### 注入配置

 修改站点配置文件`_config.yml`，添加代码如下：

```yaml
search:
  path: search.xml
  field: post
  content: true
  format: html
  limit: 10000
```

![](img\hexo1_1.png)

### 修改主题配置文件

修改主体下的D:\blog\butt\node_modules\hexo-theme-butterfly\ _config.yml（我的目录：D:\blog\butt\ _config.butterfly.yml，可以将主题下的配置文件复制粘贴到根目录下改名为 _config.butterfly.yml），搜索search，修改为如下参数

```yaml
search:
  # 选择：algolia_search / local_search / docsearch
  # 如果不需要搜索功能，保持为空
  use: local_search
  placeholder:
  
  # Algolia 搜索
  algolia_search:
    # 每页搜索结果数量
    hitsPerPage: 6

  # 本地搜索
  local_search:
    # 页面加载时预加载搜索数据
    preload: true
    # 每篇文章显示的顶部 n 个搜索结果，设置为-1 显示所有结果
    top_n_per_article: -1
    # 将 HTML 字符串反转义为可读内容
    unescape: false
    # 启用搜索结果分页
    pagination:
      enable: false
      # 每页搜索结果数
      hitsPerPage: 8
    CDN:
```

### 预览效果

开启本地server

```nginx
hexo c && hexo g && hexo s
```

访问：http://localhost:4000/ ，即可看到想要的搜索功能了

![](img\hexo1_2.png)
