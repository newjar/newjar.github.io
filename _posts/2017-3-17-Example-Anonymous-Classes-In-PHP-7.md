---
layout: post
comments: true
title: Example Anonymous Classes In PHP 7
description: "In PHP 7 Anonymous classes can now be defined using new class"
publised: true
tags: [php]
---

In PHP 7 Anonymous classes can now be defined using new class. Anonymous class can be used in place of a full class definition.

### Example
```php
<?php
   interface Logger {
      public function log(string $msg);
   }

   class Application {
      private $logger;

      public function getLogger(): Logger {
         return $this->logger;
      }

      public function setLogger(Logger $logger) {
         $this->logger = $logger;
      }  
   }

   $app = new Application;
   $app->setLogger(new class implements Logger {
      public function log(string $msg) {
         print($msg);
      }
   });

   $app->getLogger()->log("Selamat Datang");
?>
```
It produces the following browser output:
```
Selamat Datang
```
