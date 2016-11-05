Yii2 DateTime formatting behavior
============================================

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist maddoger/yii2-datetime-behavior "*"
```

or add

```
"maddoger/yii2-datetime-behavior": "*"
```

to the require section of your `composer.json` file.

Usage
-----

For datetime format and timezone conversation you can use `DateTimeBehavior`.

In model behaviors for timestamp field:

```php
[
    'class' => DateTimeBehavior::className(),
    'attributes' => ['published_at'],
    'originalFormat' => 'U', //original format
    'originalTimeZone' => 'UTC', //original timezone
    
    'timeZone' => 'Europe/London', //local timezone
    'format' => 'datetime', //local format, Formatter format
]
```

Now you can use `published_at` as original attribute and `published_at_local` as user read-write attribute.

For date fields:

```php
[
    'class' => DateTimeBehavior::className(),
    'attributes' => ['birth_date'],
    'originalFormat' => 'Y-m-d',
    'format' => 'date',
    'timeZone' => 'UTC',
]
```