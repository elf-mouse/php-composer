# [Composer](https://getcomposer.org/)

```
php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php
php -r "if (hash('SHA384', file_get_contents('composer-setup.php')) === '41e71d86b40f28e771d4bb662b997f79625196afcca95a5abf44391188c695c6c1456e16154c75a211d238cc3bc5cb47') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

执行第一条命令下载下来的 `composer-setup.php` 脚本将简单的检测 `php.ini` 中的参数设置，如果某些参数未正确设置则会给出警告；然后下载最新版本的 `composer.phar` 文件到当前目录。

上述 4 条命令的作用依次是：

1. 下载安装脚本（`composer-setup.php`）到当前目录。
2. 检查安装脚本的 `SHA-384` 指纹，以防安装脚本被篡改。
3. 执行安装过程。
4. 删除安装脚本 -- `composer-setup.php` 。

## 全局安装

全局安装是将 Composer 安装到系统环境变量 `PATH` 所包含的路径下面，然后就能够在命令行窗口中直接执行 `composer` 命令了。

__Mac 或 Linux 系统__：打开命令行窗口并执行如下命令将前面下载的 `composer.phar` 文件移动到 `/usr/local/bin/` 目录下面：

```
sudo mv composer.phar /usr/local/bin/composer
```

__Windows 系统__：请在命令行中执行如下命令：

```
mkdir C:\bin
mv composer.phar c:\bin
cd C:\bin
echo @php "%~dp0composer.phar" %*>composer.bat
```

上述命令执行成功之后再将 `C:\bin` 路径加入 `PATH` 环境变量即可。最后重新打开一个命令行窗口试一试执行 `composer --version` 看看是否正确输出版本号。

## [Fix“墙”](http://pkg.phpcomposer.com/)

### 1. 修改 composer 的全局配置文件（推荐方式）

```
composer config -g repo.packagist composer https://packagist.phpcomposer.com
```

### 2. 修改当前项目的 `composer.json` 配置文件

```
composer config repo.packagist composer https://packagist.phpcomposer.com
```
