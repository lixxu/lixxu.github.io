---
title: hexo新版本和主题设置备份
date: 2023-01-09 14:48:31
tags: hexo bluelake readmore excerpt
---

参考来源:
<https://blog.zthxxx.me/post/hexo-automatic-add-readmore/>
<https://utteranc.es/>
<https://wangjiezhe.com/posts/2018-10-29-Hexo-NexT-3/>
<https://www.simon96.online/2018/10/12/hexo-tutorial/>

时隔多年, 重新拾一下blog, 因为修改了一些主题的文件, 不备份一下下次配置时又要重头开始了, 浪费时间.

当前版本用到的插件:
```yaml
"hexo": "^6.3.0",
"hexo-deployer-git": "^3.0.0",
"hexo-generator-archive": "^2.0.0",
"hexo-generator-category": "^2.0.0",
"hexo-generator-feed": "^3.0.0",
"hexo-generator-index": "^3.0.0",
"hexo-generator-sitemap": "^3.0.1",
"hexo-generator-tag": "^2.0.0",
"hexo-helper-live2d": "^3.1.1",
"hexo-renderer-ejs": "^2.0.0",
"hexo-renderer-marked": "^6.0.0",
"hexo-renderer-stylus": "^2.1.0",
"hexo-server": "^3.0.0"
```

hexo config文件:
```yaml _config.yml
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: 学会忍受孤独
subtitle: 他人笑我太疯癫, 我笑他人看不穿
description:
author: lixxu
language: zh-CN
timezone: Asia/Shanghai

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://lixxu.github.io
root: /
permalink: ":year/:month/:day/:title/"
permalink_defaults:
pretty_urls:
  trailing_index: false # Set to false to remove trailing 'index.html' from permalinks
  trailing_html: false # Set to false to remove trailing '.html' from permalinks

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:
# Scroll percent label in b2t button
scrollpercent: true

# Writing
new_post_name: :year-:month-:day-:title.md
default_layout: post
titlecase: false # Transform title into titlecase
external_link:
  enable: true # Open external links in new tab
  field: site # Apply to the whole site
  exclude: ""

filename_case: 0
render_drafts: false
post_asset_folder: true
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace: ""
  wrap: true
  hljs: false
prismjs:
  enable: false
  preprocess: true
  line_number: true
  tab_replace: ""

# Home page setting
# path: Root path for your blogs index page. (default = '')
# per_page: Posts displayed per page. (0 = disable pagination)
# order_by: Posts order. (Order by date descending by default)
index_generator:
  path: ""
  per_page: 10
  order_by: -date

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Metadata elements
## https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta
meta_generator: true
# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss
## updated_option supports 'mtime', 'date', 'empty'
updated_option: "mtime"

# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
# theme: landscape
theme: BlueLake
stylus:
  compress: true

# json local search
jsonContent:
  meta: false
  pages: false
  posts:
    title: true
    date: true
    path: true
    text: true
    raw: false
    content: false
    slug: false
    updated: false
    comments: false
    link: false
    permalink: false
    excerpt: false
    categories: false

tags: true
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/lixxu/lixxu.github.io
  branch: master

live2d:
  enable: true
  scriptFrom: local
  pluginRootPath: live2dw/
  pluginJsPath: lib/
  pluginModelPath: assets/
  tagMode: false
  log: false
  model:
    use: live2d-widget-model-wanko
  display:
    width: 300
    height: 600
    position: right
    hOffset: 0
    vOffset: -20
  mobile:
    show: true
    scale: 0.5
  react:
    opacityDefault: 0.7
    opacityOnHover: 0.2

```

主题配置文件:
```yaml themes\BlueLake\_config.yml
##########################
## Site Config Settings ##
##########################

# Theme version
version: 3.0.0

# Theme tone
dark: true # true/false
favicon: /favicon.png
banner: "images/banner.jpg"
banner-dark: "images/banner-dark.jpg"

# Header
menu:
  - page: home
    directory: .
    icon: fa-home
  - page: archive
    directory: archives/
    icon: fa-archive
  - page: about
    directory: about/
    icon: fa-user
  - page: rss
    directory: atom.xml
    icon: fa-rss

# RSS & Sitemap plugins
Plugins: hexo-generator-feed
  hexo-generator-sitemap

# Sitemap
sitemap:
  path: sitemap.xml

# Content
excerpt_link: 阅读更多
excerpt:
  depth: 10
  excerpt_excludes: []
  more_excludes: []
  hideWholePostExcerpts: true

fancybox: true
copyright:
  enable: true # display article copyright information, true/false.
  content: "转载请注明出处."

# Date_formats
date_formats:
  post: "YYYY年MM月DD日"
  idStr: "YYYYMMDDHHmmss"

# Sidebar
sidebar: right # right/left/bottom
widgets:
  - recent_posts
  - tagcloud
  - category
  - archive
  - tag
  # - links

# Widget behavior
archive_type: "yearly" # 'yearly','monthly'
archive_format: "YYYY年" # 'YYYY年','YYYY年MM月'
show_count: true
recent_posts_limits: 5

# Toc
toc:
  enable: false
  list_number: false

# Article share
share:
  local_share: true
  baidu_share: false

# Miscellaneous
busuanzi: false ## If you want to use Busuanzi page views please set the value to true.
baidu_analytics:
google_analytics:
gauges_analytics:

# MathJax support
mathjax:
  enable: false # true/false.
  cdn: //cdn.bootcss.com/mathjax/2.7.1/latest.js?config=TeX-AMS-MML_HTMLorMML

# Reward
reward:
  enable: false # true/false 是否开启 打赏功能
  wechat: "/css/images/wechat-pay.jpg"
  alipay: "/css/images/alipay-pay.jpg"
  buttonTxt: "打赏"
  title: "“感谢你的支持，我会继续努力！”"
  content: "扫码打赏，感谢支持"

# About page
about:
  photo_url: https://avatars2.githubusercontent.com/u/264487?s=256&amp;u=04c0bc38daccfed43fc513efe5ac8440891e6029&amp;v=4 ## Your photo e.g. /themeauthor.jpg
  items:
    - label: email
      url: mailto:xuzenglin@gmail.com ## Your email with mailto: e.g.  mailto:chaoles@foxmail.com
      title: xuzenglin@gmail.com ## Your email e.g.  chaoles@foxmail.com
    - label: github
      url: https://github.com/lixxu ## Your github'url e.g.  https://github.com/chaooo
      title: lix ## Your github'name e.g.  chaooo
    # - label: weibo
    #   url: ## Your weibo's url e.g.  http://weibo.com/zhengchaooo
    #   title: ## Your weibo's name e.g.  秋过冬漫长

# Gitalk comment
gitalk:
  enable: true
  owner: lixxu ## Your GitHub ID, e.g. username
  repo: lixxu.github.io ## The repository to store your comments, make sure you're the repo's owner, e.g. gitalk.github.io
  client_id: ## GitHub client ID, e.g. 75752dafe7907a897619
  client_secret: ## GitHub client secret, e.g. ec2fb9054972c891289640354993b662f4cccc50
  admin: ## Github repo owner and collaborators, only these guys can initialize github issues.
  language: "zh-CN" ## Language
  pagerDirection: last # Comment sorting direction, available values are last and first.

# giteement评论（基于Gitee issues）【！！！慎用，Gitee接口调用时好像有次数限制，导致后面无法调试，若要使用请自行研究】
giteement:
  enable: false
  owner: #'chaoo'  # 你的码云账号英文名
  repo: #'blog-comments' # 存储评论的仓库的仓库名称(需要在码云仓库创建公开仓库)
  redirect_uri: #'https://chaoo.gitee.io'   # 应用回调地址(请和配置的第三方应用保持一致)
  client_id: #4ec96c34e83a4767d762a5a321ae15d9b8456d552c146afda829b815d51abfd2 ## GitHub client ID, e.g. 75752dafe7907a897619
  client_secret: #d2cf268817c7099b010f4ff7053f79dca3e32105da449318d8ae87f82782d531 ## GitHub client secret, e.g. ec2fb9054972c891289640354993b662f4cccc50

# Valine comment. https://valine.js.org
valine:
  enable: false # if you want use valine,please set this value is true
  appId: # leancloud application app id
  appKey: # leancloud application app key
  notify: false # valine mail notify (true/false) https://github.com/xCss/Valine/wiki
  verify: false # valine verify code (true/false)
  pageSize: 10 # comment list page size
  avatar: mm # gravatar style https://valine.js.org/#/avatar
  lang: zh-cn # i18n: zh-cn/en
  placeholder: Just go go # valine comment input placeholder(like: Please leave your footprints )
  guest_info: nick,mail,link #valine comment header info

# Changyan comment. 畅言
changyan:
  enable: false
  appid: ## changyan appid
  appkey: ## changyan appkey

# Other comments
comment:
  disqus: ## disqus_shortname
  livere: ## 来必力(data-uid)
  uyan: ## 友言(uid)
  cloudTie: ## 网易云跟帖(productKey)
  utterances:
    enable: true
    repo: lixxu/lixxu.github.io
    issue_term: pathname # pathname, url, title, og:title [ISSUE NUMBER] or [SPECIFIC TERM]
    theme: github-light


auto_excerpt:
  enable: true
  lines: 5

# Friend Links widget. Empty links will hide widget.
links:
  - title: site-name1
    url: http://www.example1.com/
  - title: site-name2
    url: http://www.example2.com/
  - title: site-name3
    url: http://www.example3.com/
```

自动添加 `read more` 修改的文件:
```html themes\BlueLake\layout\_partial\article.ejs
<article id="<%= post.layout %>-<%= post.slug %>" class="h-entry article article-type-<%= post.layout %>" itemprop="blogPost" itemscope itemtype="https://schema.org/BlogPosting">
  <div class="article-inner">
    <%- partial('post/gallery') %>
    <% if (post.link || post.title){ %>
      <header class="article-header">
        <%- partial('post/title', {class_name: 'p-name article-title'}) %>
      </header>
    <% } %>
    <div class="article-meta">
      <% if (post.top){ %>
        <span class='article-top'>【<%- __('topped') %>】</span>
      <% } %>
      <%- partial('post/date', {class_name: 'article-date', date_format: theme.date_formats.post }) %>
      <%- partial('post/category') %>
      <% if (!index){ %>
        <%- partial('post/views-count') %>
      <% } %>
      <%- partial('post/comments-count') %>
    </div>
    <div class="e-content article-entry" itemprop="articleBody">
      <% var show_all_content = true %>
      <% if (index){ %>
        <% if (post.excerpt){ %>
          <% show_all_content = false %>
          <%- post.excerpt %>
        <% } else if (theme.auto_excerpt.enable && index) { %>
          <% var br_pos = 0 %>
          <% for (var br_count = 0; br_count < theme.auto_excerpt.lines; br_count++) { %>
            <% br_pos = post.content.indexOf('\n',br_pos + 1) %>
            <% if(br_pos < 0) { break } %>
          <% } %>
          <% if(br_pos > 0) { %>
            <% show_all_content = false %>
            <p><%- post.content.substring(0, br_pos + 1) %><p>
          <% } %>
        <% } %>
      <% } else { %>
        <%- post.content %>
        <% if (!index){ %>
            <div id="toc-article">
                <%- partial('post/toc') %>
            </div>
        <% } %>
        <% if (theme.copyright.enable){ %>
          <blockquote id="copyright">
              <p><%= __("copyright_link") %>: <a href="<%- url_for(config.url +'/'+ page.path) %>"><%- url_for(config.url +'/'+ page.path) %></a></p>
              <p><%= __("copyright_notice") %>: <%= theme.copyright.content %></p>
          </blockquote>
        <% } %>
      <% } %>
    </div>
    <footer class="article-footer">
      <% if (!show_all_content || (post.excerpt && index && theme.excerpt_link)){ %>
        <%- partial('post/tag') %>
        <p class="article-more-link">
          <a href="<%- url_for(post.path) %>#more"><%= theme.excerpt_link %></a>
        </p>
      <% } else { %>
        <div class="article-tag-wrap">
          <%- partial('post/reward') %>
          <%- partial('post/tag') %>
          <%- partial('post/share') %>
        </div>
      <% } %>
      <% if (!index){ %>
        <%- partial('post/nav') %>
      <% } %>
      <% if (!index){ %>
        <%- partial('post/comments') %>
      <% } %>
    </footer>
  </div>
</article>
```

about文件
```html themes\BlueLake\layout\_partial\about.ejs
<article id="<%= post.layout %>-<%= post.slug %>" class="h-entry article article-type-<%= post.layout %>" itemprop="blogPost" itemscope itemtype="https://schema.org/BlogPosting">
  <div class="article-inner">
    <%- partial('post/gallery') %>
    <% if (post.link || post.title){ %>
      <header class="article-header">
        <%- partial('post/title', {class_name: 'p-name article-title'}) %>
      </header>
    <% } %>
    <div class="e-content article-entry" itemprop="articleBody">
      <div class="author-page">
        <div class="photo"><img src="<%= theme.about.photo_url %>"></div>
        <div class="author">
          <div><i class="fa fa-user">name：</i><%= config.author %></div>
          <% theme.about.items.forEach(function(item, i){ %>
            <div>
              <i class="fa fa-<%= item.label %>"><%= item.label %>：</i>
              <a href="<%= item.url %>" target="_blank"><%= item.title %></a>
            </div>
          <% }) %>
        </div>
        <%- post.content %>
      </div>
      <% if (!index && post.comments){ %>
        <%- partial('post/comments') %>
      <% } %>
    </div>
  </div>
</article>
```

utterances评论修改的文件:
```html themes\BlueLake\layout\_partial\post\comments-count.ejs
<% if (post.comments){ %>
<a href="<%- url_for(post.path) %>#comments" class="article-comment-link">
  <% if (!index){ %>
    <% if (theme.valine.enable && theme.valine.appId && theme.valine.appKey){ %>
      <span class="post-comments-count valine-comment-count" data-xid="<%- url_for(post.path) %>" itemprop="commentCount"></span>
    <% } %>
    <% if (theme.comment.disqus){ %>
      <i class="disqus-comment-count" data-disqus-identifier="<%- url_for(post.path) %>"></i>
    <% } %>
    <% if (theme.comment.utterances){ %>
      <a href="<%- url_for(post.path) %>" id="utterances_count_unit"></a>
    <% } %>
    <% if (theme.comment.uyan){ %>
      <a href="<%- url_for(post.path) %>" id="uyan_count_unit"></a>
    <% } %>
    <% if (theme.comment.cloudTie){ %>
      <i class="cloud-tie-join-count">
        <i class="join-count"></i>
      </i>
    <% } %>
    <% if (theme.changyan.enable && theme.changyan.appid && theme.changyan.appkey){ %>
      <i id="changyan_count_unit" data-xid="<%- url_for(post.path) %>"></i>
    <% } %>
  <% } %>
  <i class="fa fa-commt"></i>
  <%= __('guestbook') %>
</a>
<% } %>
```

```html themes\BlueLake\layout\_partial\post\comments.ejs
<% if (theme.gitalk.enable && theme.gitalk.client_id && theme.gitalk.client_secret){ %>
  <div id="comments"></div>
<% } %>
<% if (theme.giteement.enable && theme.giteement.client_id && theme.giteement.client_secret){ %>
  <div id="comments"></div>
<% } %>
<% if (theme.valine.enable && theme.valine.appId && theme.valine.appKey){ %>
  <section id="comments" class="vcomment"></section>
<% } %>
<% if (theme.comment.disqus){ %>
  <div id="comments"><div id="disqus_thread"></div></div>
<% } %>
<% if (theme.comment.livere){ %>
  <div id="comments"><div id="lv-container" data-uid="<%= theme.comment.livere %>" data-id="city"></div></div>
<% } %>
<% if (theme.comment.uyan){ %>
  <div id="comments"><div id="uyan_frame"></div></div>
<% } %>
<% if (theme.comment.cloudTie){ %>
  <div id="comments"><div id="cloud-tie-wrapper" class="cloud-tie-wrapper"></div></div>
<% } %>
<% if (theme.changyan.enable && theme.changyan.appid && theme.changyan.appkey){ %>
  <div id="comments"><div id="SOHUCS" sid="<%= page.path %>"></div></div>
<% } %>
<% if (theme.comment.utterances.enable && theme.comment.utterances.repo && theme.comment.utterances.issue_term){ %>
  <div id="comments" class="comments">
    <script src="https://utteranc.es/client.js"
        repo="<%= theme.comment.utterances.repo %>"
        issue-term="<%= theme.comment.utterances.issue_term %>"
        theme="<%= theme.comment.utterances.theme %>"
        crossorigin="anonymous"
        async>
    </script>
  </div>
<% } %>
```

自定义评论主题css
```css themes\BlueLake\source\css\style.styl

.utterances
  max-width: none

```

先就这样吧.
