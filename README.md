# PHP5 simple html parser

Usable wrapper for [simple_html_dom](http://simplehtmldom.sourceforge.net/)

Makes you happy to use simple_html_dom with your IDE

Usage
-----

Add to your composer.json

```
"require": {
    "zvook/php5-simple-html": "*"
}
```

Example

```php
use SimpleHtml\Dom;

$dom = Dom::str_get_html('<html></html>');
$dom = Dom::file_get_html('http://www.google.com/');

$div = $dom->getElementById('id1');
foreach ($div->getElementByTagName('table.table-class')->find('tr') as $row) {
    $firstCell = $row->find('td', 0);
    $thirdCell = $row->find('td', 2);
    $content = $thirdCell->plaintext;
}
```