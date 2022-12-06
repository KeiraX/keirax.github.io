---
title: Git环境配置
date: 2022-12-07 01:35:00
tags:
---

## 安装Git

- [Git下载地址](https://git-scm.com/downloads)
- [TortoiseGit下载地址](https://tortoisegit.org/download/)

## 重置Git账号密码

- 来源：[git提交代码权限问题报错记录](https://blog.csdn.net/qq_33326449/article/details/91363694)
- 报错信息
    ```
  git.exe push --progress "origin" master:master
  remote: HTTP Basic: Access denied
  fatal: Authentication failed for 'http://gitlab.xxxxxxx.com/huangyufeng/zcm-cmdb.git/'
  ```
- 问题分析
    - 用户没有赋权
    - 用户密码更改
    - Tfs账号问题
- 解决方案
    - 在**管理员模式**的GitBash.exe中执行命令
    ``git config --system --unset credential.helper``
    - 永久保存密码
    ``git config --global credential.helper store``

## Git设置永久记住密码

- 来源：[TortoiseGit save user authentication / credentials - Stack Overflow](https://stackoverflow.com/questions/14000173/tortoisegit-save-user-authentication-credentials)
- 配置步骤：To use: Right click → TortoiseGit → Settings → Git → Credential. Select Credential helper: wincred - this repository only / wincred - current Windows user
- ![](https://www.dropbox.com/s/r5voc36yfxpwdb3/Git%E8%AE%BE%E7%BD%AE%E6%B0%B8%E4%B9%85%E8%AE%B0%E4%BD%8F%E5%AF%86%E7%A0%81.png?dl=1)

- 拉取远程仓库，更新远程分支
	```
    git remote update origin --prune
    >>Fetching origin
    git remote prune origin
  ```