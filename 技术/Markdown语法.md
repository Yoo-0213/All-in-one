---
创建时间: 2025-11-16T15:09:00
创建者: winki
tags:
  - 语法
---
---
## 背景介绍

Markdown 是一种轻量级标记语言，排版语法简洁，让人们更多地**关注内容本身而非排版**。通常在整理资料以及学习总结之类的事情时，使用 Markdown 编写文档无需关注这里用多少号的字体、图片该弄多大、这里是几级标题；

## Markdown编辑器
---

|  **名称**   | <center>**说明**</center>                           | <center>**下载链接**</center>                                    |
| :-------: | :------------------------------------------------ | :----------------------------------------------------------- |
|  Notion   | 可以多人协作编写的 Markdown 文本编辑器                          | [https://www.notion.com/zh-cn](https://www.notion.com/zh-cn) |
|  Typora   | 更加纯粹的 Markdown 文本编辑器，画面更简洁，没有其他繁琐的功能，导出的 PDF 也更好看 | [https://typora.io/](https://typora.io/)                     |
| Obisidian | 一句话：极高自定义插件+双链/标签为内容构建核心 + 本地化部署的 Markdown 管理软件   | [https://obsidian.md/](https://obsidian.md/)                 |
|  VScode   | 万能编辑器，神中神                                         |                                                              |

# 语法

---
## 标题语法
```
# 这是一级标题
## 这是二级标题
### 这是三级标题
```

> [!example]
> # 这是一级标题
> ## 这是二级标题
> ### 这是三级标题

<br/>

---
## 文本语法
```markdown
**这是粗体**
*这是斜体*
***这是粗体和斜体***
~~这是删除线~~
<u>这是下划线</u>
`这是代码块`
这是<sup>上标</sup>
这是<sub>下标</sub>
[这是链接](<https://www.bilibili.com>)
---
这是分割线
<center>这是居中</center>
<font color='red'>这是修改颜色</font>
[^1]这是一个简单的脚注
```

> [!example]
> **这是粗体**
> *这是斜体*
> ***这是粗体和斜体***
> ~~这是删除线~~
> <u>这是下划线</u>
> 这是<sup>上标</sup>
> 这是<sub>下标</sub>
> [这是链接](<https://www.bilibili.com>)
> ---
> 这是分割线
> <center>这是居中</center>
> <font color='red'>这是修改颜色</font>

[^1]这是一个简单的脚注

<br/>

---
## 引用语法

支持的类型
> [!note]+
> ```
> [!note]
> ```

> [!Abstract]+
> ```
> [!Abstract]
> ```

> [!info]+
> ```
> [!info]
> ```

> [!todo]+
> ```
> [!todo]
> ```

> [!tip]+
> ```
> [!tip]
> ```

> [!success]+
> ```
> [!success]
> ```

> [!question]+
> ```
> [!question]
> ```

> [!warning]+
> ```
> [!warning]
> ```

> [!failure]+
> ```
> [!failure]
> ```

> [!danger]+
> ```
> [!danger]
> ```

> [!bug]+
> ```
> [!bug]
> ```

> [!example]+
> ```
> [!example]
> ```



<br/>

---
## 列表语法
```markdown
有序列表：
	1.First
	2.Second
	3.Third
无序列表：
	- First
	- Second
	- Third
```

> [!example]
> 有序列表：
> 1. First
> 2. Second
> 3. Third
>
>无序列表：
> - First
> - Second
> - Third

<br/>

---
## 围栏代码块

````
```
这是围栏代码块
```
````

> [!example]
> ```
> 这是围栏代码块
> ```

<br/>

---
## 任务语法
```
- [x] 这是已完成任务
- [] 这是未完成任务
```

> [!example]
> - [x] 这是已完成任务
> - [] 这是未完成任务

[^1]: 这是脚注的内容
