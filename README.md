# python_baidu_spider
使用python3爬取1000个百度百科页面
一、爬虫简介
爬虫：一段自动抓取互联网信息的程序
爬虫可以从一个url出发，访问其所关联的所有的url。并从每个url指向的网页中，获取我们所需要的信息。

二、简单爬虫架构 
1.Python简单爬虫架构
（1）爬虫调度端：启动爬虫、停止爬虫、监视爬虫的运行情况。
（2）在爬虫程序中，有三个模块：
1）Url管理器：管理将要爬取的url和已经爬取的url。将待爬取的url传送给网页下载器。
2）网页下载器：将Url指定的网页下载下来，保存为一个字符串。将这个字符串传送给网页解析器进行解析。
3）网页解析器：一方面，会解释出有价值的数据；另一方面，解析出字符串中的url，将其补充到url管理器。
这三个模块，形成了一个循环。只有有未爬取的url，这个循环就会一直继续下去。


2.Python简单爬虫架构的动态运行流程

三、分别讲解各模块设计思路
1.URL管理器
作用：管理待抓取URL集合和已抓取URL集合
目的：防止重复抓取、防止循环抓取



在这里，我们选用Python的set()来实现小型的url管理器
2.网页下载器
作用：将互联网上URL对应的网页下载到本地的工具
工作流程：



3.网页解析器
作用：从网页中提取有价值的数据
从下载好的html网页或者字符串中，可以提取出url、有价值的数据。
类型：正则表达式、html.parser、BeautifulSoup、lxml
其中，BeautifulSoup这个第三方插件可以使用html.parser和lxml作为它的解析器。
其中，正则表达式是模糊匹配，另外三种则是结构化的解析。
附，结构化解析：


四、实战：使用Python爬虫抓取百度百科的1000个页面
1.分析目标
目标：百度百科Python词条相关词条网页-标题和简介
入口页：http://baike.baidu.com/view/21087.htm
URL格式：
--词条页面URL:/view/21087.htm
数据格式：
--标题：<dd class="lemmaWgt-lemmaTitle-title"><h1>***</h1></dd>
--简介：<div class="lemma-summary" label-module="lemmaSummary">***</div>
页面编码：UTF-8



还会生成一个html记录文件

