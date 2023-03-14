---
layout: default
title: Git的安装与使用
parent: 实验一：加入GitHub Classroom
nav_order: 2
---

# Git的安装与使用
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

{: .highlight}

> 由于以下内容是第一次编辑，若存在描述不清、描述错误、完成困难等情况，请联系助教解决

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

> 

---


[^1]: [菜鸟教程-Git](https://www.runoob.com/git/git-tutorial.html)
[^2]: [Bilibili-Git教程](https://www.bilibili.com/video/BV1FE411P7B3/?spm_id_from=333.337.search-card.all.click)
[^3]: [Git官方 - Book](https://git-scm.com/book/en/v2)

