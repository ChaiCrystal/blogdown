# blogdown

##运用r语言创作自己的博客


###一、引言
本文的所有理论基于**Xie yihui**创作的书本<blogdown: Creating Websites with R Markdown>，有兴趣的同学也可以[查看原文](https://bookdown.org/yihui/blogdown/)。本文旨在让多数人快速学会制作网页，因此省略一些原理性内容和对制作影响不大的内容。


###二、制作blog吧


####1，安装需要的packages
利用r语言制作blog需要安装`blogdown`,请用以下命令安装。


```     
install.packages("blogdown")     
```


除此之外，blog需要基于静态地址形成器**Hugo**才能使用，所以我们需要以下命令安装Hugo。


```     
blogdown::install_hugo()         
```

####2，形成一个实例网页

`blogdown`程序包内含一个基础主题的blog网页，可以使用以下命令创建。


```    
blogdown::new_site()      
```

该命令要求工作目录为空。


之后便形成了主题为"hugo-lithium-theme"的网页，如图一所示。可以使用命令


```
blogdown:::serve_site()
```


或者在"addin"内选择"Serve site"即可获得静态网址


![](https://bookdown.org/yihui/blogdown/images/lithium-theme.png)


图一


现在来说一下一个用`blogdown`制作的网页有什么基础构造：
1，我们可以在工作路径找到**config.toml**这个文件，该文件包含了该网页的全局设定，如下面这些命令。


```
baseurl = "/"
languageCode = "en-us"
title = "A Hugo website"
theme = "hugo-lithium-theme"

[[menu.main]]
    name = "About"
    url = "/about/"
[[menu.main]]
    name = "GitHub"
    url = "https://github.com/rstudio/blogdown"
[[menu.main]]
    name = "Twitter"
    url = "https://twitter.com/rstudio"
```
对这些选项做出的改动都会体现在网页上，可以试着动手操作试试

2，`content`文件夹包含了该网页的内容，用来储存.rmd和.md文件

3，`static`文件夹是一些文件的默认存储目录，如图片视频等。

4，`theme`文件夹含有整个网页的结构文件，一般是java语言，超出r语言范围，顾不探讨

5，`public`文件夹是在运行"Serve site"命令后产生的，即静态网页的文件夹，推荐停止运行后删除

6，可以用`addin`目录下的"new post"，产生新内容，新内容保存在`content`内


####3，主题选择

blog制作的主题有很多，具体网址为[https://themes.gohugo.io/](https://themes.gohugo.io/)。

####4，开始制作

大家肯定已经选好了想要的主题，那么我们开始吧。

首先新建一个`new_site`，`File -> New project -> new directory -> website using blogdown`建立一个project，在theme内选择自己想要的主题，然后便做好了包含自己想要主题的网页。然后在`config.toml`内更改自己的全局设置，再用`addin -> new post`添加blog的内容，然后就做好了，附上一个本文作者做的网页[https://gameclub.netlify.com](https://gameclub.netlify.com)


####5,netlify
[netlify](https://app.netlify.com/)是一个可以将你做的静态网站发布出去的网站，该网站直接可以用github账户登录，并且是免费的，只需要将`public`文件夹上传上去即可

