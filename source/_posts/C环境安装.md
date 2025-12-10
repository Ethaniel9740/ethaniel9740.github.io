---
title: C语言环境安装
date: 2023-01-01 00:00:00
updated: 2023-01-01 00:00:00
categories: 'C'
description: c代码运行环境配置
copyright_author: Ethaniel
---

## 一、编辑器mingw64(免安装)

1、配置环境步骤：

- mingw64.rar安装包：夸克网盘下载链接：https://pan.quark.cn/s/9e384a1cd896

- 第一步：解压mingw64.rar压缩包文件，解压到当前文件夹

- 第二部：配置环境变量path

![](img\C_1.png)

最后把所有的窗口点击（确定按钮）。配置完成。

第三步、测试配置是否成功。（在dos命令窗口任意目录输入）：

```shell
gcc -v
```

出现如下界面表示成功：

![](img\C_2.png)

![](img\C_3.png)

环境配置成功。

## 二、VSCODE安装

1、下载工具：https://code.visualstudio.com/

2、控制面版---程序和功能---找到vscode

![C_4](img\C_4.png)

![](img\C_5.png)

然后找到 c:\用户\具体的windows用户名(Ethan)

 选中.vscode删除(shift+del)

二、安装VSCODE过程略

三、使用vscode

 <1>安装插件

![C_6](img\C_6.png)

<2>编写代码，打开文件夹，创建文件hello.c

```c
#include<stdio.h>
int main()
{
    printf("hello c\n");
    return 0;
}
```

<3>打开终端，运行

![](img\C_7.png)

四、vscode乱码设置：

1、点设置--搜索encoding---把编码修改成gbk

![](img\C_8.png)

最后重启vscode.