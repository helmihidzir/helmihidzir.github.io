---
layout: post
title:  "How to import SQL dump into PostgreSQL?"
date:   2023-06-15 22:00:00 +0800
categories: PostgreSQL
---
Make sure to have database first before dumping the data. If you don't have database, create one inside `psql` with:

```sql
postgres=# CREATE DATABASE database_name;
```

To import sql dump into PostgreSQL:
{% highlight shell %}
$ psql -h hostname -d databasename -U username -f file.sql
{% endhighlight %}

<br>

**Reference**

[PostgreSQL Tutorial on create database](https://www.postgresqltutorial.com/postgresql-administration/postgresql-create-database/){:target="_blank"}<br>
[Stack Overflow on SQL dump into PostgreSQL](https://stackoverflow.com/a/19167015/11448522){:target="_blank"}

