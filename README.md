Yiistrap
========

Twitter Bootstrap for Yii.

## Installation

### With Composer ###

The easiest way to install Yiistrap is to use Composer.
This is assuming your Yii project is already using Composer and the autoloader.

Run the following command to require and install the extension:

```composer require marcovtwout/yiistrap ~2.0@dev```

Add the following to your application configuration:

```php
.....
'components' => array(
    .....
    'bootstrap' => array(
        'class' => '\TbApi',
    ),
),
.....
'modules' => array(
    .....
    'gii' => array(
        'class' => 'system.gii.GiiModule',
        'generatorPaths' => array('vendor.marcovtwout.yiistrap.gii'),
    ),
),
.....
```

Add the following line to your main layout in ```protected/views/layouts/main.php``` to register the necessary CSS and JavaScript files:

```php
<?php Yii::app()->bootstrap->register(); ?>
```

### Without Composer ###

Follow the above steps first, but download and unzip Yiistrap instead of requiring it through Composer.

Then you also need to add the following to your application configuration:

```php
'aliases' => array(
    'yiistrap' => __DIR__ . '/relative/path/to/yiistrap',
),
.....
'import' => array(
    .....
    'yiistrap.behaviors.*',
    'yiistrap.components.*',
    'yiistrap.form.*',
    'yiistrap.helpers.*',
    'yiistrap.widgets.*',
),
.....
```

## Usage

Documentation not updated yet, but use the current docs as a guideline:
[http://www.getyiistrap.com](http://www.getyiistrap.com)

Use the following command to generate ApiGen documentation:

```
php vendor\bin\apigen generate
```

___Note: When you use a widget, prepend a ```\``` to the filename to use autoload it through Composer:___

```php
<?php $this->widget('\TbNav', array(
    'type' => TbHtml::NAV_TYPE_TABS,
    'items' => array(
        array('label' => 'Home', 'url' => '#', 'active' => true),
        array('label' => 'Profile', 'url' => '#',),
        array('label' => 'Messages', 'url' => '#',),
    ),
)); ?>
```
