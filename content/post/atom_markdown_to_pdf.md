+++
title = "Hello world"
date = 2018-02-27
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["TIPS","post"]
categories = []
summary = "利用atom的package方便地把markdown生成排版好看的pdf，html，jpg等。"

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = "programming/atom.png"
caption = "pdf"
preview = true

+++


此前一直在用OneNote做笔记，虽然做的也是比较整洁。但OneNote一些格式调整还是不大方便。而且输出的选择也只有pdf，不方便在其它格式之间转换。另一方面，学计算机久了，也渐渐体会到开源的好处。更愿意使用像是LaTex或者是Markdown这样方便又快捷的记录方法。上个学期开始，解除了R语言之后，用了很久Rmarkdown，发现使用markdown语法可以便捷地生成像是jpg，pdf，html等格式。特定的输出也可以使用`.css`文件来调整。

除了语言以外，一个称手的编辑器也是必不可少。这里当然强推notepad++，记得当时好像是看coursera上python的课程，Guido van Rossum说推荐大家使用notepad++。于是就入了notepad++的坑，使用至今，已经成为左膀右臂。小巧精致，而又不失强大。唯一美中不足的，是插件的数量和质量都不够高。扩展性不够强。

罗老师上学期安利了一个学期的Mac和Atom。前者实在是囊中羞涩，后者的话还是趁着学期末用了下，感觉很一般了，相比NotePad++略显臃肿，而且常用功能不如NotePad++那样便利。但其强大的扩展性和深度的可定制性还是让我眼前一亮。毕竟是号称`可以编辑的编辑器`。

前几天帮忙写一个数据分析文档，以往都是使用Rmarkdown写，然后直接输出pdf。这次想着用atom的package直接试试生成pdf。

但发现了几个坑，耗费了我很久的时间，这里记录一下，留之青山待后人。

---
## 入门

使用方法如下:

- 下载安装Atom
- 在Atom的package里搜索**markdown-themeable-pdf**，安装package
- 在package里，有关于自定义输出格式的设置:
  ![custom_path](https://www.forenewhan.science/img/programming/custom_path.png)
- 打开这里目录提示的`style.css`文件。写入自己喜欢的css格式就好。
  这里还有一些其他的设置，自己看着更改，比如输出jpg，文档尺寸等。
- 用atom编辑好一个markdown文件后，使用`ctrl+shift+E`快捷键，就可以在当前目录生成pdf文件

---

## 笔记神器

一开始是用来记笔记的。鼓捣了很久，弄了一个我比较喜欢的风格。

生成效果大概这样: [读书分享会笔记](https://www.forenewhan.science/读书会报告.pdf) ，这个是我去年听大师的读书分享会整理出来的笔记。使用markdown做记录非常简单，便捷，最重要的是生成的效果也还蛮好看的。

用得多了，发现一个问题，在代码高亮的时候会出现问题。

---

## 解决高亮代码问题

使用code fencing有两种方式。

一种是默认代码:
````
```
My code goes here
```
````


一种是带高亮的:

````
```css
My css goes here
```
````

**markdown-themeable-pdf**提供了方便的代码高亮的解决方案。支持所有的语言。但在实际上，使用代码高亮，生成pdf使用的css文件不完全是上文提到的路径下的文件。

如果你只写了上文提到的一个css文件，那么你生成的代码就可能很丑。如果改了背景色，那么将会很明显，看到两个box重叠在一起。

解决方案:

- 在**C:\Users\当前用户名\.atom\packages\markdown-themeable-pdf\css**里做修改。
- 在**C:\Users\当前用户名\.atom\packages\markdown-themeable-pdf\node_modules\highlight.js\styles**目录下，找到需要的代码高亮的css文件，然后更改里面的背景色等。

---

## 我的css格式

这里把我用到的解决方案放上来。欢迎使用。有详细的使用说明。

[链接](https://github.com/ForenewHan/MarkDownCode/tree/master/Others)

注意在`footer.js`里面的名字是我的名字，记得改这个。

---

最后提一句，上文中我的那个笔记，可是满满的政治智慧啊~~干货满满的呦，但能不能体会到，随缘啦~
