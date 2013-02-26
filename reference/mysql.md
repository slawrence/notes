MySQL Notes
=================

## Logging in

* `mysql -u root -p`

## Browsing

* `show databases`
* `use <SomeDbName>`
* `show tables`
* `show columns from table`

## Dump file

* `mysql -u root -p <DB_NAME> < dump_file_name.sql`

## User commands

* Create: `CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'mypass';`
* Check privileges: `show grants for 'jeffrey'@'localhost';`
* Add admin privileges:
    * To one DB: `grant all on db1.* TO 'jeffrey'@'localhost'`
    * To all DB: `grant all on *.* to 'jeffrey'@'localhost'`

## File output

* `select * from table into outfile 'c:/somefile.txt'`

## Deleting

* `DELETE from table where column = 'value'`
* Delete everything but some condition: `DELETE from table where column <> 'value'`

## Metrics

* Count number or rows: `select COUNT(*) from table`
