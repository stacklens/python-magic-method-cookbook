![](img/header.jpg)

[![](https://img.shields.io/badge/python-3.8-orange.svg)](https://www.python.org/downloads/release/python-370/)
[![](https://img.shields.io/badge/license-CC_BY_NC_4.0-000000.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

## Python魔法方法漫游指南

**这个库是个啥？**

- 手把手级别的系列文章，介绍Python魔法方法
- 所有文章开源免费，任何人都可以下载、阅读和传播

如果你还不知道怎么使用Python中的魔法方法，阅读本系列可以帮助你提高代码效率和生活品质。

## 魔法方法简介

Python 中的魔法方法是指以双下划线开头和结尾的特殊方法，比如 `__init__` 、 `__abs__` 等。

Python 中的内置类定义了非常多的魔法方法。比如 `int` 类，你可以用 `dir()` 函数查看：

```python
>>> dir(int)
['__abs__', '__add__', '__and__', '__bool__', ...]
```

魔法方法可以直接被调用，但更多的时候，它会在特定情况下被自动调用。

就比如整数相加的计算，它实际上就相当于：

```python
>>> num = 1
>>> num + 2
3
>>> num.__add__(2)
3
```

你可以让一个自定义的类实现 `__add__` 魔法方法，从而使它也可以进行加法计算。

比如定义一个矢量：

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
    def __add__(self, other):
        new_x = self.x + other.x
        new_y = self.y + other.y
        return Vector(new_x, new_y)
```

由于实现了 `__add__` 方法，这个矢量类就可以非常自然的相加：

```python
>>> v1 = Vector(1, 2)
>>> v2 = Vector(3, 4)

>>> v3 = v1 + v2

>>> v3.x
4
>>> v3.y
6
```

总之，魔法方法在 Python 中占有重要的地位，并且涵盖了你想得到的几乎全部基础功能，灵活运用可以让你的代码更加简洁高效。

所有的魔法方法在官方文档里都可以找到，但是它非常的枯燥并且缺少示例，不太容易理解。

因此我将**常用和重要的魔法方法**归纳总结好（注意不是全部！），面向新手从基础讲起，写成这个系列文章。

希望你漫游愉快!

> 如果本系列教程对你有帮助，可通过点赞、评论、转发来支持我。

## 加入社区

一个人的学习是孤单的。欢迎扫码 Python 交流QQ群、公众号、TG群组，和大家一起进步。

![](https://blog.dusaiphoto.com/QR-0608.jpg)

此外，本系列文章也会同步发布在[我的博客](https://www.dusaiphoto.com/topic/)。博客主要发布 Python 或 Django 的教程，欢迎围观。

## 许可协议

本教程（包括且不限于文章、代码、图片等内容）遵守 **署名-非商业性使用 4.0 国际 (CC BY-NC 4.0) 协议**。协议内容如下。

**您可以自由地：**

- **共享** — 在任何媒介以任何形式复制、发行本作品。
- **演绎** — 修改、转换或以本作品为基础进行创作。

只要你遵守许可协议条款，许可人就无法收回你的这些权利。

**惟须遵守下列条件：**

- **署名** — 您必须给出**适当的署名**，提供指向本许可协议的链接，同时标明是否（对原始作品）作了修改。您可以用任何合理的方式来署名，但是不得以任何方式暗示许可人为您或您的使用背书。
- **非商业性使用** — 您不得将本作品用于**商业目的**。
- **没有附加限制** — 您不得适用法律术语或者技术措施从而限制其他人做许可协议允许的事情。

> 适当的署名：您必须提供创作者和署名者的姓名或名称、版权标识、许可协议标识、免责标识和作品链接。
>
> 商业目的：主要目的为获得商业优势或金钱回报。
