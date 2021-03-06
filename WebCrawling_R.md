## An R web crawler and scraper 
[![CRAN version](http://www.r-pkg.org/badges/version/Rcrawler)](https://CRAN.R-project.org/package=Rcrawler)
[![Build Test](https://api.travis-ci.org/salimk/Rcrawler.svg?branch=master)](https://travis-ci.org/salimk/Rcrawler)
![Downloads Stats](http://cranlogs.r-pkg.org/badges/Rcrawler)
[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)
[![DOI Paper](https://user-images.githubusercontent.com/17308124/31905494-44039a56-b826-11e7-9ace-01db4904176d.png)](https://doi.org/10.1016/j.softx.2017.04.004)

## Rcrawler is an R package for web crawling websites and extracting structured data which can be used for a wide range of useful applications, like web mining, text mining, web content mining, and web structure mining. So what is the difference between Rcrawler and rvest : rvest extracts data from one specific page by navigating through selectors. However, Rcrawler automatically traverses and parse all web pages of a website, and extract all data you need from them at once with a single command. For example collect all published posts on a blog, or extract all products on a shopping website, or gathering comments, reviews for your opinion mining studies. More than that,  Rcrawler can help you studies web site structure by building a network representation of a website internal and external hyperlinks (nodes & edges). 


## Comparison of some popular R packages for data collection.
![compare-rcrawler](https://user-images.githubusercontent.com/17308124/33799263-178f2e80-dd20-11e7-85d8-f89053ca3a94.PNG)

## Summary
1. [RCrawler main features](https://github.com/salimk/Rcrawler#rcrawler-main-features)

2. [Installation](https://github.com/salimk/Rcrawler#installation)

3. [How to use Rcrawler (Tutorials)](https://github.com/salimk/Rcrawler#how-to-use-rcrawler)

4. [Design and Implementation](https://github.com/salimk/Rcrawler#design-and-implementation)

5. [How to cite Rcrawler](https://github.com/salimk/Rcrawler#how-to-cite-rcrawler)

6. [Updates history](https://github.com/salimk/Rcrawler#brief-on-updates)

## RCrawler main features  

With one single command **Rcrawler function** enables you to :

- Download all website's HTML pages, ([see 1](https://github.com/salimk/Rcrawler#1--collecting-web-pages-from-a-website))

- Load collected HTML Files to R environement (memory) ([see 2](https://github.com/salimk/Rcrawler#2--loading-collected-html-files-to-memory-r-environment))

- Extract structured DATA from all website pages: Titles, posts, Films, descriptions, products...etc ([see 3](https://github.com/salimk/Rcrawler#3-crawl-and-scrape-data-from-a-website-pages))

- Scraping targeted contents using search terms, by providing desired keywords Rcrawler can traverse all wbesite links and collect/extract only web pages related to your topic. ([see 4](https://github.com/salimk/Rcrawler#4-filter-collected-scraped-web-page-by-search-termskeywords))
 
Some websites are so big, you don't have sufficient time or ressources to crawl them, So you are only interested in a particular section of the website for these reason we provided some useful parameters to control the crawling process such as : 

- Filtering collected/scraped Urls by URLS having some keywords or matching a specific pattern ([see 5](https://github.com/salimk/Rcrawler#5--filtering-collectedparsed-urls-by-regular-expression)) 

- Control how many levels Should be crawled from the start point .([see 6](https://github.com/salimk/Rcrawler#6-liming-the-crawling-process-to-a-level-maxdepth-parameter)) 

- Choose to ignore some URL parameters during crawling process ([see 7](https://github.com/salimk/Rcrawler#7-ignore-some-url-parameters-ignoreurlparams))  

In Web structure mining field Rcrawler provide some starter kit to analyze the web site network.

- Represent a website Netwok by mapping all its internal and external hyperlink connections (Edges & nodes) ([see 8](https://github.com/salimk/Rcrawler#8-creating-a-website-network-graph))

In addtition, Rcrawler package provide a set of tools that makes your R web mining life easier:

- Scrape data from a list of URLs you provide ([see 9-1](https://github.com/salimk/Rcrawler/#9-1--scrape-you-list-of-urls))

- Exclude an inner element (node) from scraped data ([see 9-2](https://github.com/salimk/Rcrawler#9-2--exclude-an-inner-element-node-from-scraped-data))
 
## Installation 

Install the release version from CRAN:
```
install.packages("Rcrawler")
```
Or the development version from GitHub:
```
# install.packages("devtools")
devtools::install_github("salimk/Rcrawler")
```
Citation
> R Web Crawling by Salim K. Retrieved March 15, 2018, 
from https://github.com/salimk/Rcrawler
