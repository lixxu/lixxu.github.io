---
title: 使用 utterances 作为评论系统
comments: true
date: 2019-03-20 16:36:10
tags:
 - utterances
 - jade
 - pug
categories: blog
---
参考来源: <https://wangjiezhe.com/posts/2018-10-29-Hexo-NexT-3/>

今天在 [蟒周刊](http://weekly.pychina.org/issue/issue-359.html) 里看到使用了 [utterances](https://utteranc.es) 作为评论系统, 网上查了一下, 原来是基于 `github` 的. 于是我也跟风配置了一下, 就不用 [disqus](https://disqus.com) 了, 毕竟只能用梯子才能访问.

由于我用的是 [BlueLake](https://github.com/chaooo/hexo-theme-BlueLake), 里面的模板用的是 [Jade](http://jade-lang.com/), 根本不熟悉 (好像新版用 [pug](https://pugjs.org/api/getting-started.html) 代替 `Jade` 了). 在 [SO](https://stackoverflow.com/questions/8698534/how-to-pass-variable-from-jade-template-file-to-a-script-file)看到传递参数的语法是 `#{variable_name}`.

最后, 总算搞定了.
1. 在文件 `themes\BlueLake\layout\_partial\comments.jade` 的最后添加
```jade

if theme.comment.utterances.enable
  #comments.comments
    script(type="text/javascript",src="https://utteranc.es/client.js",charset="utf-8",repo="#{theme.comment.utterances.repo}",issue-term="#{theme.comment.utterances.issue_term}",theme="#{theme.comment.utterances.theme}",crossorigin="anonymous",async=true)
```

2. 打开主题评论的配置选项:
```
comment:
  duoshuo: #chaooo ## duoshuo_shortname
  disqus: ## disqus_shortname
  livere: ## 来必力(data-uid)
  uyan: ## 友言(uid)
  cloudTie: ## 网易云跟帖(productKey)
  utterances:
    enable: true
    repo: owner/repo
    issue_term: pathname # pathname, url, title, og:title [ISSUE NUMBER] or [SPECIFIC TERM]
    theme: github-light
  changyan: ## 畅言需在下方配置两个参数，此处不填。
    appid: ## 畅言(appid)
    appkey: ##畅言(appkey)
```
