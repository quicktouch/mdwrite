> gitbook是一个写作和出版的平台，他们使用的系统是开源的。支持Markdown和AsciiDoc格式，最后输出的是静态网页。

知识是一个缓慢积累的过程，系统性的知识总结/教程,可用使用[gitbook](https://www.gitbook.com)发布成(共开/私有)的书籍。 

例如: [简单易懂的npm教程](https://legacy.gitbook.com/book/dkvirus/-npm/details)、[flutter实战](https://book.flutterchina.club)等。  国内也有与gitbook类似的平台如:[看云](https://www.kancloud.cn)

## gitbook的简单使用 [参考](http://www.chengweiyang.cn/gitbook/installation/README.html)

### 注册gitbook、并授权github仓库

见图片。
设置为以github仓库为主,gitbook根据仓库的内容更新。

### 安装gitbook-cli

```bash
npm install  gitbook-cli -g
```
### 初始化书籍

1. cd 到书籍目录
2. 初始化`gitbook init`

```bash
cd <你的目录>
gitbook init
Installing GitBook 3.2.3
#...
#info: create README.md
#info: create SUMMARY.md
#info: initialization is finished
```
### 编写文档

上步骤初始化结束,目录下生成了`README.md`、`SUMMARY.md`两个文档。其中`README.md`存放整个文档的描述,`SUMMARY.md`存放目录

gitbook预览的命令为: 
```
gitbook serve
```

1). 修改文档`SUMMARY.md`内容

```
# Summary

<!-- 描述图书的目录结构 -->

* [Introduction](README.md)
* [markdown](markdown/README.md)
* [编辑器推荐](编辑器推荐/README.md)
* [图床](图床/README.md)
* [gitbook](gitbook/README.md)
```

2). 添加图书章节内容,添加完成后目录为:

```bash
── README.md
├── SUMMARY.md
├── _book（由自动gitbook自动生成,请无视）
│   └── 略
├── gitbook
│   └── README.md
├── markdown
│   └── README.md
├── 图床
│   └── README.md
└── 编辑器推荐
    └── README.md
```

### 提交/发布

- 可以直接分享gitbook链接,如:[https://tyrad.gitbook.io/mdwrite/](https://tyrad.gitbook.io/mdwrite/) 
- 可以生成静态文件(`gitbook build --output=/tmp/gitbook`),部署到个人服务器或githubpages上
- 可以导出pdf、epub、mobi

代码提交到github上对应的仓库(`注册gitbook、并授权github仓库`步骤中授权的仓库。注意提交的分支与授权时的分支一致)。   
因为webhook的存在,gitbook中会有最新提交的显示效果。


可以导出各种格式的电子书,需要先安装插件[ebook-convert](https://calibre-ebook.com/download)
```bash
#默认生成再当前项目的跟目录上
gitbook pdf

# 生成 `pdf` 文件并输出 `debug` 级别日志
gitbook pdf  ./myBook.pdf --log=debug

# 生成 `epub` 文件并输出 `debug` 级别日志
gitbook epub ./ ./myBook.epub --log=debug

# 生成 `mobi` 文件并输出 `debug` 级别日志
gitbook mobi ./ ./myBook.mobi --log=debug
```

### 其他扩展

gitbook支持添加评论插件、自定义主题等,这里不再赘述。