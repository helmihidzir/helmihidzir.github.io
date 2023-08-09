---
layout: post
title: "Update and Delete in Clickhouse"
date: 2023-08-09 23:22:00 +0800
categories: Clickhouse
---

Update command
```sql
ALTER TABLE <table_name> UPDATE col1 = expr1, ... WHERE <filter>;
```

Delete command
```sql
ALTER TABLE <table_name> DELETE WHERE <filter>;
```

<br/>

**Reference**

[Updates and Deletes in ClickHouse](https://altinitydb.medium.com/updates-and-deletes-in-clickhouse-d5df6f336ce9){:target="_blank"}<br>