---
layout: post
title:  "Create user in MySQL"
date:   2020-11-16 22:51:03 -0300
categories: software
---

```shell
mysql -uroot
```

Inside of mysql shell

```shell
CREATE USER 'helio'@'localhost' IDENTIFIED BY '12345678';
```

*helio* is the **User** and *12345678* is the **Password**

```shell
GRANT ALL PRIVILEGES ON * . * TO 'helio'@'localhost';
```

The first star is the database (in this case, all databases). The second star are the tables (In this cases all tables)

**ALL PRIVILEGES** permit all operations on this database.

```shell
FLUSH PRIVILEGES;
```

Possible permitions:

+ ALL PRIVILEGES
+ CREATE
+ DROP
+ DELETE
+ INSERT
+ SELECT
+ UPDATE
+ GRANT OPTION


To revoke permissions

```shell
REVOKE ALL PRIVILEGES ON * .* FROM 'helio'@'localhost';
```


ALTER USER 'helio'@'localhost' IDENTIFIED BY '12345678';
ALTER USER 'helio'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';
