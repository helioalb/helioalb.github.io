---
layout: post
title:  "You must enable the intl extension to use CakePHP"
date:   2020-11-20 08:45:03 -0300
categories: software
---

# You must enable the intl extension to use CakePHP

This is a common error when running CakePHP.

First install php-intl:

```shell
sudo apt-get update
```

```shell
sudo apt-get install php-intl
```

In the php.ini (/etc/php/7.2/apache2/php.ini) uncomment the line `extension=intl`.
