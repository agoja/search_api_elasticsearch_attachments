# Search API Elasticsearch Attachments
[![CircleCI](https://circleci.com/gh/dakkusingh/search_api_elasticsearch_attachments.svg?style=svg)](https://circleci.com/gh/dakkusingh/search_api_elasticsearch_attachments)

Elasticsearch is generally used to index data of types like string,
number, date, etc.
However, what if you wanted to index a file like a .pdf or a .doc
directly and make it searchable?

This module allows Drupal to index files (attachments) to Elasticsearch by
making use of Elasticsearch data type "attachment".

![Search_API_Elasticsearch_Attachments](https://www.drupal.org/files/search_api_elasticsearch_attachments.jpg)

## Requirements
This module requires:
* Drupal 8
* Search API Module
* Elasticsearch Connector module (8.x-5.x)
* Elasticsearch Version 5.6
* Elasticsearch `ingest-attachment` plugin

## Elasticsearch Plugin Installation
The first step is to install the Elasticsearch plugin: `ingest-attachment`,
which enables ES to recognise the "attachment" data type. In turn, it uses
Apache Tika for content extraction and supports several file types such as
.pdf, .doc, .xls, .rtf, .html, .odt, etc.

```
$ES_HOME> bin/elasticsearch-plugin install ingest-attachment
```
Thats the hard work done.

## Install this module with composer
```
composer require drupal/search_api_elasticsearch_attachments
```

## Elasticsearch Connector module (5.x) compatibility.
8.x-5.0-alpha3 version of Elasticsearch Connector module requires a number of patches.
If you are using 5.x, please use 8.x-5.x-dev of
*search_api_elasticsearch_attachments* module.

This will auto install the *search_api_elasticsearch_attachments* module
and also install the *elasticsearch_connector* module

There are a number of patches required to elasticsearch_connector module.
These are applied automatically by composer.
Sit back and let composer do the hard work for you. Patches that will
get auto applied by composer:
* Issue #2918138 by dakku: Support for alterParams()

## Elasticsearch Attachments Configuration
### Enable and Configure the Elasticsearch Attachments Processor
![Enable_the_Processor](https://www.drupal.org/files/Screen_Shot_2017-12-19_at_11_39_06_pm.jpg)
