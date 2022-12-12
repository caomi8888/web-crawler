## 一、目标：

1.掌握scrapy框架作用及其运行流程

2.掌握scrapy框架每个模块的作用

3.利用scrapy框架进行爬虫

## 二、知识要点

### 1.什么是Scrapy

Scrapy是用纯python实现一个为了爬取网站数据，提取结构性数据而编写的应用框架，用途非常广泛。

### 2.为什么要学习Scrapy

- scrapy基于事件的机制，异步存储方式极大的提高了爬虫的效率
- 配置简单，通过简单代码实现复杂爬虫

### 3.Scrapy常用命令

#### 3.1常用命令

```python
# 查看帮助(全部命令以及其描述)
scrapy --help
#创建一个新的Scrapy项目(项目名不可以以数字开头)
scrapy startproject <project_name>
#在当前文件下或者当前项目，创建一个新的爬虫文件
scrapy genspider example example.com
#运行一个爬虫文件
scrapy runspider spider_name
#获取指定的url,并且能够显示出获取的过程
scrapy fetch url
#在浏览器中打开指定的url
scrapy view url
#查看scrapy版本 参数-v会将关联模块一并输出
scrapy version [-v]
```

#### 项目命令

```python
#运行爬虫项目
scrapy crawl spider
#测试本地硬件性能
scrapy bench
#列出当前项目下的所有爬虫文件
scrapy list
```

## 3.2创建项目

## 4.Scrapy核心框架

### 按照功能划分：

Scrapy Engine:

- Scheduler(调度器)
- Downloader(下载器)
- Spiders(爬虫)
- Item Pipeline(数据管道)

![image-20221126165804179](https://tva1.sinaimg.cn/large/008vxvgGgy1h8iyzpsov1j30nj0bajs2.jpg)

![image-20221126165819333](https://tva1.sinaimg.cn/large/008vxvgGgy1h8iyzxp27gj30o70h3758.jpg)

 其中爬虫(解析)和数据管道(数据保存)需要自己手动去编写，调度器和下载器已经帮我们写好了。

**引擎**：总指挥：负责数据和信号在不同组件之间传递 已实现

**调度器**： 一个队列，存放引擎发过来的request请求 已实现

**下载器**： 下载引擎发过来的request请求并且将响应返回给引擎

**爬虫**： 处理引擎发送来的response 提取数据，提取url，再交给引擎

​                                                                                                  需要手写

**管道**：处理引擎发送来的数据 比如存储 需要手写

**下载中间件**：可以自定义下载扩展，比如设置代理 一般不用手写

**爬虫中间件**：可以自定义request请求和进行response过滤 一般不用手写

###  5.Scrapy的使用

#### 5.1Scrapy的项目流程

1.创建项目：scrapy startproject项目名称

2.明确目标：明确要爬取的目标

3.编写爬虫：编写爬虫代码，开始爬取网页

4.存储内容：设计管道存储爬取内容

5.启动程序：类似之前写的main函数，此处可以是命令也可以是文件

5.2爬取美剧天堂





Scrapy crawl meiju -o Meiju.csv将爬取到的东西存入csv file

​                                   -o meiju.json/xml都可以

5.2基于管道的持久化(重点)

- 在items.py文件中进行定义相关持久性属性
- 在爬虫文件中将解析的数据存储到item类型对象中
- 将items类型对象提交给管道
- 在管道文件中，接受爬虫文件提交过来的items类型
- 对持久化数据进行几定义形式存储
- 在配置文件中打开管道机制



### Yield:

如果一个函数用了yield,可以将函数变成一个generator生成器

def main():
	for i in range(10):

​		yield i

这个main()已经变成一个生成器了

main().__next__()

或者可以放在循环里

for i in main():
	print(i)

就可以以0，1，2，3，4，5，6，7，8，9来生成

六、总结

scrapy常用方法：

Response.xpath()利用xpath解析数据

extract()返回一个包含有字符串的列表

extract_first()返回列表中的第一个字符串，列表为空没有返回None