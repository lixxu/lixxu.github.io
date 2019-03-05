---
title: 保存 git 密码
date: 2017-12-20 16:27:28
tags: git
---
每次 pull 仓库时, 都要输入密码, 太麻烦了. 记录保存一下 (明文存储的密码, 安全要求高的考虑其他方法吧).

文章来自于: <https://stackoverflow.com/questions/5343068/is-there-a-way-to-skip-password-typing-when-using-https-on-github>

You can also have Git store your credentials permanently using the following:

`git config credential.helper store`

Note: While this is convenient, Git will store your credentials in clear text in a local file (`.git-credentials`) under your project directory (see below for the "`home`" directory). If you don't like this, delete this file and switch to using the cache option.

If you want Git to resume to asking you for credentials every time it needs to connect to the remote repository, you can run this command:

`git config --unset credential.helper`
To store the passwords in `.git-credentials` in your `%HOME%` directory as opposed to the project directory: use the `--global` flag

`git config --global credential.helper store`

Windows 平台下可以使用 <https://github.com/Microsoft/Git-Credential-Manager-for-Windows>, 在第一次需要输入密码时会弹窗, 输入后下次就不用输入了.
