Symfony Demo Application in Docker
==================================

The "Symfony Demo Application in Docker" is a project application for a [tutorial][2] based on [Symfony Demo Application][1].
The tutorial explain you how to set-up a Symfony project in **Docker** environment. 

Requirements
------------

  * PHP 7.2.9 or higher;
  * SQLite;
  * Docker.

Installation
------------

Clone this repository in your machine:

```bash
https://github.com/clemdesign/docker-symfony-demo.git
```

Install dependencies:

```bash
cd docker-symfony-demo
composer install
```

Run Docker:

```bash
docker-compose up -d
```

Migrate SQLite database to MySQL database - [Guide][3]:

```bash
goto data
sqlite3 database_old.sql .dump > dump.sql
cat dump.sql | python sqlite-to-mysql.py > dump-mysql.sql
```

Then import `dump-mysql.sql` file in the Docker Mysql Database <http://localhost:8080/>.


Usage
-----

When environement is installed and configured, start Docker is not yet:

```bash
docker-compose up -d
```

Access to application at <http://localhost:8000>.

Access to PhpMyAdmin database management at <http://localhost:8080>.

Tests
-----

Execute this command to run tests:

```bash
$ cd my_project/
$ ./bin/phpunit
```

License
-------

Copyright 2020 Clemdesign.

Under MIT License.

[1]: https://github.com/symfony/demo
[2]: https://clemdesign.fr/blog/2020/docker-configurer-un-projet-symfony-partie-1-deployer-php-fpm-et-nginx
[3]: https://clemdesign.fr/blog/2020/docker-configurer-un-projet-symfony-partie-3-migrer-une-base-sqlite-vers-mysql
