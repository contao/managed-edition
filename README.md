Contao 4 managed edition
========================

Contao is an Open Source PHP Content Management System for people who want a
professional website that is easy to maintain. Visit the [project website][1]
for more information.


System requirements
-------------------

Contao requires:

* A webserver with rewrite support (such as Apache with mod_rewrite or nginx)
* PHP Version 7.1.0 (or greater)
  * with the following extensions:
    * gd
    * dom
    * Phar
    * intl
    * mbstring (optional, better performance if native)
  * make sure the following functions are available:
    * proc_open
    * proc_close
* Database
  * MySQL 5.5.7 (or greater)
    * InnoDB with innodb_large_prefix enabled
  * MariaDB (or greater)

InnoDB large prefix
-------------------

MySQL versions prior to 5.7.7 do not have the `innodb_large_prefix` option
enabled by default. To enable it in one of these versions, add the following
to your `my.cnf` file:

```
innodb_large_prefix = 1
innodb_file_format = Barracuda
innodb_file_per_table = 1
```

If the option cannot be enabled on your server, please configure a different
database engine and character set in your `app/config/config.yml` file:

```yml
doctrine:
    dbal:
        connections:
            default:
                default_table_options:
                    charset: utf8
                    collate: utf8_unicode_ci
                    engine: MyISAM
```


Installation
------------

See the [installation chapter][2] of the user's manual.


Documentation
-------------

 * [User's manual][3]
 * [Developers's manual][4]
 * [Cookbook][5]
 * [API reference][6]


License
-------

Contao is licensed under the terms of the LGPLv3.


Getting support
---------------

Visit the [support page][7] to learn about the available support options.


[1]: https://contao.org
[2]: https://docs.contao.org/books/manual/current/en/01-installation/installing-contao.html
[3]: https://docs.contao.org/books/manual/current/
[4]: https://docs.contao.org/books/extending-contao4/
[5]: https://docs.contao.org/books/cookbook/
[6]: https://docs.contao.org/books/api/
[7]: https://contao.org/en/support.html
