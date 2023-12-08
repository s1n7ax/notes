# Databases

## List databases

`\l` - list the databases (following 3 databases are default databases)

```
postgres=# \l
                                                      List of databases
   Name    |  Owner   | Encoding | Locale Provider |  Collate   |   Ctype    | ICU Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+------------+------------+------------+-----------+-----------------------
 postgres  | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 template0 | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/postgres          +
           |          |          |                 |            |            |            |           | postgres=CTc/postgres
 template1 | postgres | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/postgres          +
           |          |          |                 |            |            |            |           | postgres=CTc/postgres
```

## Create database

```sql
# CREATE DATABASE <name>;
CREATE DATABASE test;
```

## Connect to database

### Method 1

```shell
# psql -h <host> -p <port> -U <uesr> <database>
psql -h 0.0.0.0 -p 5432 -U root test
```

### Mothod 2

```shell
# \c <database>
\c test
```

## Delete database

```
# drop database <database>;
drop database test;
```
