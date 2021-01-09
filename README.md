# Pymed Tutorial

✒️ [English](./README.md)| [中文](./README_CN.md)

# PyMed - PubMed Access through Python
PyMed is a Python library that provides access to PubMed through the PubMed API.

## Background
The PubMed API is not very well documented and querying it in a performant way is too complicated and time consuming for researchers. This wrapper provides access to the API in a consistent, readable and performant way.

## Install

```shell
pip install pymed
```

## Features
This library takes care of the following for you:

- Querying the PubMed database (with the standard PubMed query language)
- Batching of requests for better performance
- Parsing and cleaning of the retrieved articles

## Examples
For full (working) examples have a look at the `examples/` folder in this repository. In essence you only need to import the `PubMed` class, instantiate it, and use it to query:

```python
from pymed import PubMed
pubmed = PubMed(tool="MyTool", email="my@email.address")
results = pubmed.query("Some query", max_results=500)
```
#### Tips

#### Here is some infos will help your user search builder

>Using the search words builder
>
>Click [Advanced search](https://pubmed.ncbi.nlm.nih.gov/advanced/) and use the search builder.
>
>In here you can contribute searching query, and there is some **History and Search Details**

#### Example warning

> In python scripts, two words link with 'AND'. 
>
> In web pages, it is 'OR' when searching in [pubmed](https://pubmed.ncbi.nlm.nih.gov/). 
>
> The different in search results, therefor you should care for use 'AND' and 'OR' words. 

### here is some bugs need to fix

> In results, json key: 'pubmedid' occur to like this `"pubmed_id": "33163806\n19615749\n10899625\n6294088\n24905783\n27081112\n25620698\n1988040\n26970376\n9570564\n32405284\n32264791\n19648270\n8896442\n22178917\n20889553\n30244324\n29664642\n32274522\n27177653\n27666013\n32027979\n17653609\n29652924\n19077082\n21788983\n7021592\n2841359\n7593196\n21079042\n19278419\n10733101\n21553931",`
>
> Just the first number is the correct pubmedid. 
>
> The others are reference papers' pubmedid.

## Notes on the API
The original documentation of the PubMed API can be found here: [PubMed Central](https://www.ncbi.nlm.nih.gov/pmc/tools/developers/). PubMed Central kindly requests you to:

> - Do not make concurrent requests, even at off-peak times; and
> - Include two parameters that help to identify your service or application to our servers
>   * _tool_ should be the name of the application, as a string value with no internal spaces, and
>   * _email_ should be the e-mail address of the maintainer of the tool, and should be a valid e-mail address.

## Notice of Non-Affiliation and Disclaimer 
The author of this library is not affiliated, associated, authorized, endorsed by, or in any way officially connected with PubMed, or any of its subsidiaries or its affiliates. The official PubMed website can be found at https://www.ncbi.nlm.nih.gov/pubmed/.

## Maintainers

[@hotwa](https://github.com/hotwa)

## Contributing

[@gijswobben](https://github.com/gijswobben)

[@radusuciu](https://github.com/radusuciu)

[@Darkbladecr](https://github.com/Darkbladecr)

[@esteininger](https://github.com/esteininger)

## License

[MIT](https://github.com/hotwa/pymed/blob/master/LICENCE) © hotwa

## Others

>Welcome Fork,Star,Issues, I will try to solve the related problems.
>
>If you have other communication about medical and pharmaceutical data analysis, you can add my qq group: 816163664

Recommend parsing JSON can be used with [JmesPath](https://github.com/jmespath/jmespath.py) library is more convenient to use.

You can build your own scripts by referring to other related github projects that parse PubMed.

[pubmed_parser](https://github.com/titipata/pubmed_parser)

[pubmedCrawler](https://github.com/Tomatenbiss/pubmedCrawler)