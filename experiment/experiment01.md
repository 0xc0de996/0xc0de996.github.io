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

本课程的采用GitHub Classroom发布实验任务。GitHub Classroom是GitHub提供的一个教育工具，而GitHub是基于Git版本控制系统的代码托管平台。

下面简要介绍下Git、GitHub以及GitHub Classroom。 

**Git 简介**

Git是一种分布式版本控制系统，可以用于跟踪和管理代码的变更历史记录。Git最初由Linus Torvalds创建，主要用于管理Linux内核的代码。

Git的主要特点是分布式管理，即每个用户都可以在自己的本地计算机上拥有完整的代码仓库，并且可以将本地仓库同步到远程仓库中。这使得多个用户可以同时在同一个项目上进行开发，而不必依赖中央服务器。Git还支持多个分支，使得开发人员可以在不干扰主要开发分支的情况下进行实验性的开发和测试。

Git具有强大的分支和合并功能，可以让开发人员轻松地在不同分支之间切换，并将代码合并回主分支。它还具有丰富的工具集，包括可视化工具、代码审查工具和补丁管理工具等，这些工具可以帮助开发人员更好地管理代码库。

由于Git具有广泛的使用和强大的功能，它已成为了现代软件开发的标准工具之一。

**GitHub 简介**

GitHub是一个基于Git版本控制系统的代码托管平台，它提供了一个云端仓库，让开发者可以存储、管理和共享他们的代码。

GitHub不仅仅是一个代码托管平台，它还提供了很多强大的协作工具，如问题追踪、代码审查、分支管理、团队协作、集成测试等，这些工具可以帮助开发者更加高效地进行协作开发。此外，GitHub还提供了强大的社交网络功能，让开发者可以在平台上互相交流和学习。

GitHub是开源社区的重要组成部分，许多开源项目都托管在GitHub上，这使得开源项目的开发、贡献和分享变得更加容易。GitHub还提供了很多有用的功能，如自动化构建、持续集成、自动化部署等，这些功能可以帮助开发者更加高效地构建和发布软件。

总而言之，GitHub为开发者提供了一个全面的、高效的平台，使他们可以更加轻松地进行协作开发、学习和分享。

**GitHub Classroom 简介**

GitHub Classroom是GitHub提供的一个教育工具，旨在为教师和学生提供一个集中管理和提交代码的平台。

使用GitHub Classroom，教师可以轻松地创建课程作业、分配任务和评估学生的工作。教师可以在GitHub上创建一个课程作业，设置截止日期和其他要求，并将作业分配给学生。学生可以通过GitHub Classroom加入课程并获取课程作业，然后在自己的GitHub仓库中完成作业并提交到指定的分支上。

GitHub Classroom还提供了一些额外的功能，如自动化代码审查、批量打分、实时反馈等，这些功能可以帮助教师更加高效地管理和评估学生的作业。

## Git安装与使用

### Windows系统

1. 访问[Git官网](https://git-scm.com/downloads)，下载 Git 的 Windows 版本。
2. 运行安装程序，按照提示进行安装。在选择安装选项时，建议选择默认选项。
3. 打开终端输入`git --version`， 如果安装成功，将会显示Git版本号

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

建议先学习Git的基本原理[^1][^2]，Git官网提供了完整的教程[^3]，这里仅介绍我们未来会使用到的Git命令。

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



{: .warning }
> This website documents the features of the current `main` branch of the Just the Docs theme. See [the CHANGELOG]({% link CHANGELOG.md %}) for a list of releases, new features, and bug fixes.



> 以上内容若有任何问题，请联系助教

---


[^1]: [Git菜鸟教程](https://www.runoob.com/git/git-tutorial.html)
[^2]: [Git最新教程通俗易懂bilibili](https://www.bilibili.com/video/BV1FE411P7B3/?spm_id_from=333.337.search-card.all.click)
[^3]: [Git - Book (git-scm.com)](https://git-scm.com/book/en/v2)
