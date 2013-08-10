docX-templates
==============
[![Build Status](https://travis-ci.org/tyz910/docx-templates.png?branch=master)](https://travis-ci.org/tyz910/docx-templates)
[![Latest Stable Version](https://poser.pugx.org/tyz910/docx-templates/v/stable.png)](https://packagist.org/packages/tyz910/docx-templates)

You can create a .docx template file with included search-patterns that can be replaced by any value you wish:

```php
<?php
use DocxTemplate\TemplateFactory;

$template = TemplateFactory::load('template1.docx');
$template->assign([
    'name'    => 'Jon',
    'surname' => 'Snow',
    'house'   => 'Stark'
]);
$template->save('jon.docx');
```

Search-pattern spelling
-----------------------

Default search-pattern spelling is: **{{mark_name}}**  
Mark name should be lowercase, with words separated by underscores.

    My name is {{name}}.
    
Also you can use any search-pattern spelling you wish:

```php
<?php
use DocxTemplate\TemplateFactory;

TemplateFactory::setMarkPattern('${%s}'); // %s will be replaced with mark name
$template = TemplateFactory::load('template.docx');
```

## Installation using [Composer](http://getcomposer.org/)

Add to your `composer.json`:

```json
{
    "require" :  {
        "tyz910/docx-templates": "*"
    }
}
```
