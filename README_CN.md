# Pymed Tutorial

✒️ [English](./README.md)| [中文](./README_CN.md)

# PyMed - 通过Python获取PubMed数据

## 背景

Pubmed API并没有完善的开发者文档并且在使用的过程中太过于复杂，并且对研究者而言会消耗大量的时间。

PyMed 封装提供了以一致的、可读的和高性能的方式使用PubMed数据抓取。

## 安装

```shell
pip install pymed
```

## 特性

该库为您提供以下服务。

- 查询PubMed数据库（使用标准的PubMed查询语言）。
- 批量处理请求以提高性能
- 对检索到的文章进行解析和清理。

## 例子

对于具体的例子可以参考该库目录`examples/`，你只需要导入`Pubmed`类，初始化，然后使用：

```python
from pymed import PubMed
pubmed = PubMed(tool="MyTool", email="my@email.address")
results = pubmed.query("Some query", max_results=500)
```

### 技巧

> 搜索关键词构建

> 通过高级搜索获得查询参数query（string）点击[链接](https://pubmed.ncbi.nlm.nih.gov/advanced/)

此链接可以看到你在PubMed搜索的历史记录（网页端）

#### 注意

> 在初始的query字符参数里面使用的连接词为'**AND**'，实际网页端搜索两个关键词连接词为'**OR**'，根据自己的实际需求不同使用连接词。（搜索结果不一致）

#### 一些待修复的bug

> 在一些检索的结果中在json的pubmedid键值出会出现像：`"pubmed_id": "33163806\n19615749\n10899625\n6294088\n24905783\n27081112\n25620698\n1988040\n26970376\n9570564\n32405284\n32264791\n19648270\n8896442\n22178917\n20889553\n30244324\n29664642\n32274522\n27177653\n27666013\n32027979\n17653609\n29652924\n19077082\n21788983\n7021592\n2841359\n7593196\n21079042\n19278419\n10733101\n21553931",`
>
> 只有第一个为正确该文章的pubmedid，其余则为参考引用文献的pubmedid。

## 关于API的说明

PubMed API的原始文档可以在这里找到。[PubMed Central](https://www.ncbi.nlm.nih.gov/pmc/tools/developers/)希望使用该服务时：

> - 不要同时提出请求，即使在非高峰期也不要；
> - 包括两个参数，帮助我们的服务器识别您的服务或应用程序。
> _tool_应该是应用程序的名称，是一个没有内部空格的字符串值，并且
> _email_应该是工具维护者的电子邮件地址，并且应该是一个有效的电子邮件地址。

## 非隶属关系通知和免责声明 

本文库的作者与PubMed或其任何子公司或附属机构没有任何关系、关联、授权、认可或任何形式的正式联系。PubMed的官方[网址](https://www.ncbi.nlm.nih.gov/pubmed/)。

## 维护者

[@hotwa](https://github.com/hotwa)

## 贡献者

[@gijswobben](https://github.com/gijswobben)

[@radusuciu](https://github.com/radusuciu)

[@Darkbladecr](https://github.com/Darkbladecr)

[@esteininger](https://github.com/esteininger)

## 许可

[MIT](https://github.com/hotwa/pymed/blob/master/LICENCE) © hotwa

## 其他

欢迎Fork,Star,Issues，我会尝试解决相关问题。

如果有其他关于医疗医药数据分析交流，可以添加我的qq群：816163664

推荐解析JSON可以搭配[JmesPath](https://github.com/jmespath/jmespath.py)库更加利于使用

可以参考其他相关的解析PubMed的github项目构建您自己的脚本：

[pubmed_parser](https://github.com/titipata/pubmed_parser)

[pubmedCrawler](https://github.com/Tomatenbiss/pubmedCrawler)



