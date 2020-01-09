Using db.sql
============

File 'db.sql' is meant to be imported to sqlite3 with command:

`sqlite3 ip.sqlite < output/db.sql`

Subnets should be searched in `subnet_all` view with normalized IP's converted to binary form like this:

```
sqlite> select country_code, country_name, continent_code, continent_name from subnet_all where start <= X'291324F3' and `end` >= X'291324F3';`
ZA|South Africa|AF|Africa
```

Same queries work for IPv4 and IPv6 in binary form