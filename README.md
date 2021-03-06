Yii2 Module for data analysts
============================

Construction of complex sections of data in tabular form.

[Здесь документация на Русском языке](https://github.com/anmoroz/yii2-analytics/tree/master/docs)

Requirements
------------

* PHP >= 5.4.0.
* Elasticsearch 1.7.2
* yiisoft/yii2 ~2.0
* yiisoft/yii2-bootstrap ~2.0
* ruflin/elastica ~2.2.1
* bower-asset/select2 ~4.0

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist anmoroz/yii2-analytics
```

or add

```json
"anmoroz/yii2-analytics": "~0.0.1"
```

to the require section of your composer.json.

Configuration
-------------

Edit the configuration file (web.php), for example:

In section "module"
```php
'analytics' => [
    'class' => 'anmoroz\analytics\Module',
    'configClass' => 'app\components\AnalystsConfigurator',
    'dbAdapterName' => 'db',
    'elasticSearch' => [
        'host' => 'localhost',
        'port' => '9200',
        'debug' => false
    ]
]
```
Edit the configuration file (console.php) as web.php, and additionally in section "bootstrap"
```php
'bootstrap' => ['analytics']
```

Create AnalystsConfigurator exstends anmoroz\analytics\components\AbstractConfigurator

Indexing data
-------------

Execute the `php yii analytics/indexation` command

![yii2-analytics schema](https://raw.github.com/anmoroz/yii2-analytics/master/docs/screenshots/yii2-analytics-schema.jpg)
