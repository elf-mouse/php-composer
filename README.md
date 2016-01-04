# [Composer](https://getcomposer.org/)

## Installation - Linux / Unix / OSX

* Run these commands to globally install `composer` on your system:

```
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
```

> Note: If the above fails due to permissions, run the `mv` line again with sudo.

* A quick copy-paste version including sudo:

```
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

Now just run `composer` in order to run Composer instead of php `composer.phar`.

```
composer -V
```

## [Fix“墙”](http://pkg.phpcomposer.com/)

```
composer config -g repositories.packagist composer http://packagist.phpcomposer.com
```
