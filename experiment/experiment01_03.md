---
layout: default
title: 加入GitHub Classroom
parent: 实验一：加入GitHub Classroom
nav_order: 3
---

# 加入GitHub Classroom
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

{: .highlight}

> 由于以下内容是第一次编辑，若存在描述不清、描述错误、完成困难等情况，请联系助教解决

## 加入GitHub Classroom

在登录GitHub后，点击[链接](https://classroom.github.com/a/AaiacQ2l)，加入GitHub Classroom完成第一次实验。进入页面后点击自己的姓名绑定自己的GitHub账号，如下图所示。

<img src="C:\Users\11248\Desktop\0xc0de996.github.io\img\join classroom.png" width = "800" alt="加入课堂" align=center/>

{: .note}

> 若绑定错误，请联系助教解决

## Hello World

绑定账户后，会自动跳转到第一次的实验**Hello World**，点击绿色的`Accept this assignment`后，等待几秒会提示一个作业仓库链接（请刷新页面），如下图所示。

<img src="C:\Users\11248\Desktop\0xc0de996.github.io\img\accept assignment.png" width = "800"  alt="接受任务" align=center />

<img src="C:\Users\11248\Desktop\0xc0de996.github.io\img\accept assignment2.png" width = "800"  alt="接受任务" align=center />

将该仓库clone到本地进行代码编写。

```shell
git clone 你的项目地址
```

在第一次实验中，请修改`experiment01/main.py`中的`main`函数，使其返回`Hello, World!`，注意**不要修改**同目录下的`text.py`文件，将修改好的文件上传到GitHub中，GitHub会进行自动的判分处理。

```shell
git add .
git commit -m "第一次提交"
git push
```

在提交后，下图红框中棕色的点代表代码正在执行，若通过测试则变成绿色的钩子，若未通过测试则变为红色的叉，同时会收到GitHub发送的测试失败邮件（通过则无）。

<img src="C:\Users\11248\Desktop\0xc0de996.github.io\img\commit.png" width = "800" alt="提交作业" align=center/>

{: .note}

> 只要仓库内的文件有更新就会执行一次新的测试，你可以无限次的提交代码，以最后一次的提交做最终成绩

{: .warning}

> 注意本次实验截止到北京时间04/01/2023 00:00，过期无法提交，请务必在截至日期前完成实验，否则影响后续的所有实验

{: .congratulations}

> 恭喜完成本次实验](https://git-scm.com/book/en/v2)

