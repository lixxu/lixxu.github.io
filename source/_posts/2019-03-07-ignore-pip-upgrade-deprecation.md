---
title: 忽略 pip 在 python2.7 上的废弃警告
comments: true
date: 2019-03-07 12:42:41
tags:
- python
- pip
categories: python
---

新版的 `pip` 在 `python2.7` 上使用时, 会显示废弃的信息.
{% asset_image pip.png %}

看着比较烦人, 网上有解决方案 <https://github.com/pypa/pip/pull/6147#issuecomment-457910432>.

具体做法是:
新建一个 `PYTHONWARNINGS` 的环境变量, 值设为 `ignore:DEPRECATION::pip._internal.cli.base_command`, `Windows` 下两边没有双引号, 其他平台可能需要.

重新启动命令行, 再跑一下, 应该就没有了.
{% asset_image pip_ok.png %}
