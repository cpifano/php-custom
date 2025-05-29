# ![logo](./img/logo.png)
**PHP Custom** is a docker image of an old version of **PHP (5.6)** with old dependencies already resolved.



#### Dependencies resolved:

* [GD](https://www.php.net/manual/en/book.image.php)
* [MySQLi](https://www.php.net/manual/en/book.mysqli.php)
* [libpng](http://www.libpng.org/pub/png/libpng.html)



---



## Deploy

Example `docker-compose.yml` content:

```yaml
services:
  php-custom:
    container_name: php-custom
    image: cpifano/php-custom:1.0.1
    restart: unless-stopped
    volumes:
        - ./php/conf:/usr/local/etc/php/
        - ./php/src:/var/www/html
    ports:
      - 80:80
```



---



## License

**PHP Custom** is licensed by [MIT](https://choosealicense.com/licenses/mit/).
