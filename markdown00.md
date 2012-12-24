## Markdown
###  what is markdown?
轻量级标记语言，标签类似于html
### why markdown
* 简单    语法不多
* 流行    github的readme,stackflow均支持markdown
* 易读    不像html有很多tag
### 亮点
### markdown如何转成pdf
使用gimli 用ruby写的工具

install: 安装过程要在网上去下载3个不大的包

    yum install rubygems ruby-devel gcc libxml2-devel libxslt-devel
    gem install gimli
use:

    gimli -f file.md
### markdown本地预览 github 风格
[grip](https://github.com/joeyespo/grip)
```
yum install pip-python
pip install grip
```
### markdown 可以做什么
* github README
* 写博客
* 随手记
* 纯文本笔记

### 怎样写markdown
markdown本身是带标记的纯文本，任何纯文本编辑器都可以书写；也有在线编辑器   
pandoc 在线转换成html 可用来测试语法 
### 语法
[官网](http://daringfireball.net/projects/markdown/syntax)
[中文语法](http://wowubuntu.com/markdown/)
markdown中可以直接使用html，比如table
#### 标题
setext风格，只支持 h1 h2   
使用 = - 标识，数量多少都可以

    this is an H1
    ============

    this is an H2
    -------------
atx风格 用#数量定义标题   
支持 h1-h6,末尾也可以用任意数量的#闭合标题 

    # H1
    ## H2
    ### H3
    #### H4
    ##### H5
    ###### H6
#### 引用区块 被解析成`<quote></quote>`
引用的文本会缩进显示，支持嵌套引用,引用内部支持其他markdown语法
<pre>
> this is blockquote
> > this is a blockquote in blockquote
> > ## this is a H2 in blockquote
</pre>
#### 列表
##### 无序列表
用 * + - 都可以标识

    * list1
    * list2
    * list3
##### 有序列表
用数字接着一个英文句点定义。   
列表中的数字不影响输出的HTML结果。   
列表内的段落和引用都需要缩进。

    1. list1
    4. list2
    2. list3
会解析成

    <ol>
    <li>list1</li>
    <li>list2</li>
    <li>list3</li>
    </ol>
用转义称号避免不必要的列表,1999\.
#### 代码区块
缩进4个空格或1个tab即可,代码区块延续到没有缩进的那一行
#### 分隔线
用3个以上的 * - _ 定义

    * * *
    ***
    ----------
    _______________
#### 区段元素
##### 链接
行内式   
\[链接文本](链接地址)

    [example](http://test.com)
示例: [example](http://test.com)

参考式   
\[链接文本][链接标识]
\[链接标识]: 链接地址 "title"

    [example][1]
    [1]: http://test.com "test.com"
示例: [example][1]
[1]: http://test.com "test.com"
##### 强调
用 * _ 包围字词即可

    *word*
    _word_
##### 行内代码
    `code`
##### 图片
语法与链接类似   
行内式

    ![alt text](url/to/image)
参考式

    ![alt text][id]
    [id]: url/to/image
#### 其他
##### 自动链接
用尖括号包起来会自动转成链接 <http://test.com>
##### 反斜杠
\ 转义特殊字符
