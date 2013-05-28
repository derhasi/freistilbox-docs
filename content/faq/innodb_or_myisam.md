---
title: "Which MySQL storage engine should i use?"
---

# Which MySQL storage engine should i use?

Definitively use InnoDB. InnoDB is in many aspects superior to MyISAM
and offers a multitude of tuning possibilities. InnoDB also allows for
consistent online backups without locking database access. Drupal 7 and
up already uses InnoDB by default.

For these reasons, our hosting environment is optimized for InnoDB and
**we support only the InnoDB storage engine**. If your database schema still
uses MyISAM tables, you should convert them to InnoDB. We've explained
below how to do that.

## Converting a database from MyISAM to InnoDB
### Using SQL

On your local MySQL server, you can convert the database tables easily
with the `ALTER TABLE` command:

`ALTER TABLE tablename ENGINE=INNODB;`

Then you can do a database dump and transfer that onto our hosting
platform.

### Using the DB Tuner module

With DB Tuner, there’s a Drupal module that allows you (among other
things) to convert MySQL tables to InnoDB.

### Let our team do the conversion

Alternatively, we can convert your tables directly on the hosting
platform; simply send us a [support request](http://support.freistil.it).
