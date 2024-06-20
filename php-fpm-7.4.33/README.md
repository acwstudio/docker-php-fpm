# Alpine PHP-FPM [![Build Status](https://api.cirrus-ci.com/github/joseluisq/alpine-php-fpm.svg)](https://cirrus-ci.com/github/joseluisq/alpine-php-fpm) [![Docker Image](https://img.shields.io/docker/pulls/joseluisq/php-fpm.svg)](https://hub.docker.com/r/joseluisq/php-fpm/)

> [PHP-FPM](https://www.php.net/manual/en/install.fpm.php) (PHP [7.4](https://www.php.net/ChangeLog-7.php#PHP_7_4)) with essential extensions on top of [Alpine Linux 3.15](https://alpinelinux.org/).

### <span style="color:red">  Important preface </span>

I'm not a very good at installation and configuration of PHP extensions, so I have taken a lot of ideas and files from [https://github.com/joseluisq/alpine-php-fpm](https://github.com/joseluisq/alpine-php-fpm)
If you are interested in using ready docker images and configurations of different web servers (Apache, NGINX) look at the link above. 


### PHP 7.4

![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/joseluisq/php-fpm/7.4) ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/joseluisq/php-fpm/7.4)

### Built-in extensions

`curl`, `ftp`, `hash` (`mhash`), `libedit`, `libsodium`, `mbstring`, `mysqlnd`, `openssl`, `password-argon2`, `pdo-sqlite`, `pear`, `sqlite3`, `zlib`

### Additional extensions

| Extension  |  v7.4  |
|------------|:------:|
| amqp       |   ✓    |
| apcu       |   ✓    |
| bcmath     |   ✓    |
| bz2        |   ✓    |
| exif       |   ✓    |
| gd         |   ✓    |
| gettext    |   ✓    |
| gmp        |   ✓    |
| imagick    |   ✓    |
| imap       |   ✓    |
| intl       |   ✓    |
| mcrypt     |   ✓    |
| memcache   |   ✓    |
| mongodb    |   ✓    |
| mysqli     |   ✓    |
| oauth      |   ✓    |
| pcntl      |   ✓    |
| pdo_dblib  |   ✓    |
| pdo_mysql  |   ✓    |
| pdo_pgsql  |   ✓    |
| pgsql      |   ✓    |
| psr        |   ✓    |
| soap       |   ✓    |
| sockets    |   ✓    |
| ssh2       |   ✓    |
| tidy       |   ✓    |
| vips       |   ✓    |
| xmlrpc     |   ✓    |
| xsl        |   ✓    |
| yaml       |   ✓    |
| swoole     |   ✓    |
| sysvmsg    |   ✓    |
| sysvsem    |   ✓    |
| sysvshm    |   ✓    |
| zip        |   ✓    |
| &nbsp;     | &nbsp; |
| **Others** |        |
| composer   |  v2.4  |

**Footnotes**

(?) It means that this extension is obsolete/unmaintained/discourage or simply is not supported yet.

## Usage

### Build an image and run a container

```sh
# build fpm 7.4.33 image
make build-fpm-7.4.33
# run container
make start-phpinfo-7.4.33
# symlink to your project
make symlink-phpinfo-7.4.33
```

## Default Paths

- Default Docker working directory: `/var/www/html`
- Additional PHP `.ini` files to load: `/usr/local/etc/php/conf.d`
- Custom PHP `.ini` file generated (only if `ENV_SUBSTITUTION_ENABLE=true`): `/usr/local/etc/php/conf.d/default-php.ini`

## Configurable Environment Variables

**PHP-FPM** and **PHP** configurations can be overwritten using environment variables.
To do it so, just indicates the substitution of values using `ENV_SUBSTITUTION_ENABLE=true` (since it is disabled by default).

Below the environment variables with their default values:

### PHP-FPM

#### Global FPM

Settings replaced into `/usr/local/etc/php-fpm.conf` file.

- `PHP_FPM_ERROR_LOG=/proc/self/fd/2`
- `PHP_FPM_LOG_LEVEL=error`

#### FPM WWW Pool

Settings replaced into `/usr/local/etc/php-fpm.d/www.conf` file.

- `PHP_FPM_LISTEN=9000`
- `PHP_FPM_USER=www-data`
- `PHP_FPM_GROUP=www-data`
- `PHP_FPM_LISTEN_OWNER=www-data`
- `PHP_FPM_LISTEN_GROUP=www-data`

### PHP Config

Settings replaced into `/usr/local/etc/php/conf.d/default-php.ini` file (`php.ini`).

- `PHP_MEMORY_LIMIT=512M`
- `PHP_EXPOSE_PHP=On`
- `PHP_SESSION_GC_MAXLIFETIME=1440`

