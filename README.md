IPGeo
-----

Daily updated free database of subnet-country pairs usable in various purposes. It is open, lightweight and less accurate alternative to Maxmind's GeoLite (without latitude and longitude).

- all country/continents codes are presented in ISO 3166-1 alpha-2
- entries are in CIDR notation

## ipgeo-country.mmdb
- drop-in replacement for GeoLite2-Country
- names in English included only
- example result `{"country": {"iso_code": "CZ", "names": {"en": "Czech republic"}}, "continent": {"iso_code": "EU", "names": {"en": "Europe"}}}`

## db.sql
- 'db.sql' is meant to be imported to sqlite3 with command:
   
   `sqlite3 ip.sqlite < output/db.sql`

   Subnets should be searched in `subnet_all` view with normalized IP's converted to binary form like this:
   
  ```
  sqlite> select country_code, country_name, continent_code, continent_name from subnet_all where start <= X'291324F3' and `end` >= X'291324F3';`
  ZA|South Africa|AF|Africa
  ```

  Same queries work for IPv4 and IPv6 in binary form


## *.csv
- comma delimited csv export