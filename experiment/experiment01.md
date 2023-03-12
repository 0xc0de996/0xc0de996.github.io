---
layout: default
title: 实验一：加入GitHub Classroom 
parent: Experiments
nav_order: 1
---

# 加入GitHub Classroom
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## GitHub Classroom 简介

本课程的采用GitHub Classroom发布实验任务。GitHub和GitHub Classroom都建立在Git技术基础之上，GitHub是一个基于Git的代码托管平台，而GitHub Classroom是一个基于GitHub的在线教育工具，用于管理和评估学生的编程作业。下面简要介绍下Git、GitHub以及GitHub Classroom。 

**Git 简介**

[Git](https://git-scm.com/)是一种分布式版本控制系统，用于跟踪文件和目录的更改。它通过在本地计算机上保存完整的代码仓库来工作，使得团队协作和离线工作变得容易。Git具有分支和合并功能，使团队可以并行工作并最终将其代码合并为一个整体。Git还有很多功能，例如可撤销的提交、标记版本、处理文件冲突等。在开源社区和商业领域中，Git已成为最受欢迎的版本控制系统之一。

**GitHub 简介**

[GitHub](github.com)是一个基于Git版本控制系统的代码托管平台，可以让开发者在互联网上分享和协作开发代码。它提供了许多功能，如代码托管、版本控制、代码审查、问题跟踪、Wiki和协作工具等。通过GitHub，开发者可以共享和学习其他人的代码，并与其他开发者协作开发项目。GitHub也是一个开源社区，任何人都可以在上面发布和维护开源软件。它已成为全球最大的开源社区之一，得到了广泛的应用和支持。

**GitHub Classroom 简介**

[GitHub Classroom](https://classroom.github.com/)是一个基于GitHub的在线教育工具，为教育机构提供了一个统一的平台来管理和评估学生的编程作业。教师可以使用GitHub Classroom来创建作业、分发作业、监控学生的进度、评估作业和反馈。学生可以使用GitHub Classroom来接收作业、提交作业、查看反馈和与教师互动。GitHub Classroom使教育机构可以更高效地管理和评估学生的编程作业，同时也为学生提供了一个实践编程技能的机会。

## Git安装与使用

### Windows系统

1. 访问[Git官网](https://git-scm.com/downloads)，下载 Git 的 Windows 版本。
2. 运行安装程序，按照提示进行安装。在选择安装选项时，建议选择默认选项。
3. 打开终端输入`git --version`， 如果安装成功，将会显示Git版本号



{: .note}

> 若安装完成后，`git --version`无法显示git版本号，则需要将安装目录下/bin加入环境变量

### Linux系统

- Ubuntu/Debian

  1. 打开终端

  2. 输入 `sudo apt-get update` 命令以更新软件包列表。
  3. 输入 `sudo apt-get install git` 命令以安装Git。

  4. 在终端窗口中输入 `git --version` 命令，如果安装成功，将会显示Git版本号。

- CentOS / Fedora

  1. 打开终端窗口。

  2. 输入 `sudo yum update` 命令以更新软件包列表。

  3. 输入 `sudo yum install git` 命令以安装Git。

  4. 在终端窗口中输入 `git --version` 命令，如果安装成功，将会显示Git版本号。

### Mac系统

1. 打开终端窗口。
2. 输入 `brew install git` 命令以安装Git（如果您未安装Homebrew，请先安装Homebrew）。
3. 在终端窗口中输入 `git --version` 命令，如果安装成功，将会显示Git版本号。

## GitHub访问加速与账号注册

1. 使用[网易UU加速器](https://uu.163.com/)，选择`学术资源`可免费加速GitHub
2. 使用[Steam++](http://steampp.net/)，可免费加速GitHub



{: .note}

> 完成访问加速后，访问[GitHub](https://github.com)按照要求完成注册即可。

GitHub支持`Https`和`SSH`两种同步方式，前者做过多配置，但每次上传代码都需要输入自己的账户和密码，这部分介绍如何使用SSH同步。

1. 打开终端输入以下命令：

    ```shell
    git config --global user.name = "xxxx"  # 用户标识符
    git config --global user.email = "xxx@xxx"  # 填写GitHub的注册邮箱
    ```

2. 创建SSH key：

    ```shell
    ssh-keygen
    ```

    在windows系统下，默认会在`我的文档/.ssh`目录下生成`id_rsa`文件和`id_rsa.pub`文件，使用文本编辑器打开`id_rsa.pub`，复制内容

3. 进入[GitHub](https://github.com)，点击右上角的头像->`Settings`->`Access/SSH and GPG keys`->`New SSH key `，将ssh公钥复制到`Key`一栏中。

## Git的使用

{: .warning}

> 建议先学习Git的基本原理[^1][^2]，Git官网提供了完整的教程[^3]，这里仅介绍我们未来会使用到的Git命令。

1. 克隆远程仓库：打开一个github仓库，例如该[仓库]([0xc0de996/0xc0de996.github.io: HHU-ANN-2023](https://github.com/0xc0de996/0xc0de996.github.io))，点击绿色的`Code`按钮，可以选择`HTTPS`或`SSH`方式克隆

    ```shell
    git clone https://github.com/0xc0de996/0xc0de996.github.io.git  # HTTPS
    git clone git@github.com:0xc0de996/0xc0de996.github.io.git # SSH，需要提前配置SSH
    ```

2. 添加文件：在仓库中添加要跟踪的文件，可以使用以下命令：

    ```shell
    git add <文件名>  # <文件名>可以使用.代替，意味着提交该目录下的所有文件
    ```

3. 提交变更：在将更改保存到仓库之前，需要将它们提交。可以使用以下命令提交变更：

    ```shell
    git commit -m "提交说明"
    ```

4. 查看仓库状态：可以使用以下命令查看当前仓库的状态：

    ```shell
    git status
    ```

5. 远程仓库：将本地仓库推送到远程仓库，以便与其他人协作。可以使用以下命令将本地仓库推送到远程仓库，在本次实验中，修改克隆后的仓库只需`git push`推送即可（需拥有仓库权限）：

    ```shell
    git remote add <远程仓库名> <远程仓库URL>
    git push -u <远程仓库名> <本地分支名>
    ```

{: .note }

> 在实验中，需要clone远程的模板仓库到本地，完成代码提交到远程仓库进行自动评分，在此过程中需要用到`git clone` `git add` `git commit`和`git push`即可

## 加入GitHub Classroom

在登录GitHub后，点击[链接](https://classroom.github.com/a/AaiacQ2l)，加入GitHub Classroom完成第一次实验。进入页面后点击自己的姓名绑定自己的GitHub账号，如下图所示。

<img src="..\img\join classroom.png" width = "600" alt="加入课堂" align=center/>

{: .note}

> 若绑定错误，请联系助教解决

绑定账户后，会自动跳转到第一次的实验**Hello World**，点击绿色的`Accept this assignment`后，等待几秒会提示一个作业仓库链接（请刷新页面），如下图所示。

<img src="..\img\accept assignment.png" width = "600"  alt="接受任务" align=center />

<img src="..\img\accept assignment2.png" width = "600"  alt="接受任务" align=center />

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

<img src="..\img\commit.png" width = "600" alt="提交作业" align=center/>

{: .warning}

> 注意本次实验截止到北京时间04/01/2023 00:00，过期无法提交，请务必在截至日期前完成实验

{: .note}

> 只要仓库内的文件有更新就会执行一次新的测试，你可以无限次的提交代码，以最后一次的提交做最终成绩

{: .congratulations}

> 恭喜完成本次实验。

{: .highlight}

> 由于以上内容是第一次编辑，若存在描述不清、描述错误、完成困难、等情况，请联系助教解决。
>
> 请务必完成以上内容，否则无法完成后续的所有实验。

---


[^1]: [菜鸟教程-Git](https://www.runoob.com/git/git-tutorial.html)
[^2]: [Bilibili-Git教程](https://www.bilibili.com/video/BV1FE411P7B3/?spm_id_from=333.337.search-card.all.click)
[^3]: [Git官方 - Book](https://git-scm.com/book/en/v2)
