---
title: jQuery Chosen异常CSS的修复
comments: true
date: 2019-03-04 09:30:41
tags: jquery chosen
categories: web
---
背景:
1. jquery 3.3.1
2. chosen 1.8.7
3. bootstrap 3.4.1


在使用 [chosen](https://harvesthq.github.io/chosen/) 时, 在给选择框加错误提示时, 边框的颜色没有变:
{% asset_image no-border-error.png %}

研究了一下, 最后参考 SO 上的答案, 在自定义的 CSS 文件里加入以下几行:
```css
.chosen-container-single .chosen-single {
  height: 38px;
  line-height: 38px;
}
.chosen-container-single .chosen-single div b {
  background: url(chosen-sprite.png) no-repeat 0 8px;
}
.chosen-container-single .chosen-search input[type=text] {
  min-height: 36px;
}

div.form-group.has-error div div a.chosen-single {
  border-color: #b94a48;
}
```
最后的显示算是正常了:
{% asset_image ok.png %}

注意: 这个方法在 `bootstrap4` 上无效.
