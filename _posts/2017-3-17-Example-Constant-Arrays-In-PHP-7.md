---
title: "Example Constant Arrays In PHP 7"
layout: post
tag:
- Php
comments: true
author: nurulfajar
---
Array constants can now be defined using the define() function. In PHP 5.6, they could only be defined using const keyword.

### Example
```php
<?php
   //define a array using define function
   define('animals', [
      'dog',
      'cat',
      'bird'
   ]);
   print(animals[1]);
?>
```

It produces the following browser output:
```
cat
```
