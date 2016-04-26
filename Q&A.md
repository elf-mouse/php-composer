## Q&A

Q: `composer`

```
PHP Fatal error:  Uncaught exception 'PharException' with message 'phar "/usr/local/bin/composer" has a broken signature' in /usr/local/bin/composer:23
```

A: reinstall

---

Q: `composer update`

```
The following exception is caused by a lack of memory and not having swap configured
Check https://getcomposer.org/doc/articles/troubleshooting.md#proc-open-fork-failed-errors for details

PHP Fatal error:  Uncaught exception 'ErrorException' with message 'proc_open(): fork failed - Cannot allocate memory' in phar:///usr/local/bin/composer/vendor/symfony/console/Application.php:950
```

A: To enable the swap you can use for example:

```
/bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024
/sbin/mkswap /var/swap.1
/sbin/swapon /var/swap.1
```

---

Q: `[Composer\Downloader\TransportException] Your configuration does not allow connection to http://packagist.phpcomposer.com. See https://getcomposer.org/doc/06-config.md#secure-http for details.`

A: `composer.json`

```
"config": {
    "secure-http": false
}
```

---

Q:

```
[ReflectionException]
Class Fxp\Composer\AssetPlugin\Repository\NpmRepository does not exist
```

A:

```
composer global update fxp/composer-asset-plugin --no-plugins
```
