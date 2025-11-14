---
title: SQL
---

[SQL](https://en.wikipedia.org/wiki/SQL) is a standard interface language for relational databases.

[MySQL](https://www.mysql.com/) has been the most prevalent implementation found in past competitions.

## Quick Reference

### System

Determine which sql program is running
```sh
ps aux | grep sql
```


Log into a MySQL server (`--help` and [cli docs](https://dev.mysql.com/doc/refman/8.4/en/connecting-disconnecting.html))
```bash
# Login as <username>. Will prompt for a password
mysql -u <username> -p
```


MySQL supports batch execution and plays nice with redirection
```bash
mysql < batch-file > mysql.out
```

!!! example
    List default creds and also where to find them if they have been changed

### Database

List databases

```sql
SHOW DATABASES;
```

Find any PII (add / remove clauses as needed)

```sql
SELECT TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME
FROM information_schema.COLUMNS
WHERE COLUMN_NAME LIKE '%user%'
   OR COLUMN_NAME LIKE '%pass%'
   OR COLUMN_NAME LIKE '%cred%'
   OR COLUMN_NAME LIKE '%secret%'
   OR COLUMN_NAME LIKE '%key%'
   OR COLUMN_NAME LIKE '%ssn%'
   OR COLUMN_NAME LIKE '%email%'
   OR COLUMN_NAME LIKE '%phone%'
   OR COLUMN_NAME LIKE '%address%';
```

[Common examples from MySQL](https://dev.mysql.com/doc/refman/8.4/en/examples.html)

## Notes

`INFORMATION_SCHEMA` is your best friend when searching for specific info in a large pile of databases and tables.
It functions as a "meta-table", meaning it holds information on all of the other tables.

`LIKE` and `GLOB` are similarly extremely useful for quick searching.

## Resources
- [W3Schools](https://www.w3schools.com/sql/) - pretty good. Can serve as a concise and quick-to-scan reference, or a longer-winded tutorial when you have the time
- [SQLZoo](https://sqlzoo.net) - practice your skills here
