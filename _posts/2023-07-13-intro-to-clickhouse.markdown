---
layout: post
title:  "Intro to Clickhouse"
date:   2023-07-13 23:30:00 +0800
categories: Clickhouse
---

#### **What is Clickhouse**
Clickhouse is column database. <br/><br/>
Clickhouse is Online Analytical Processing (OLAP) Database. <br/><br/>
Usually use for analytics and logging monitoring. <br/><br/>
Syntax feels similar to Relational Databases like PostgreSQL and MySQL. <br/><br/>
Main feature is able to analyze millions of data in seconds. <br/><br/>
Main feature is able to analyze millions of data in seconds. <br/><br/>
If not specify engine will default to MergeTree. <br/><br/>
It is normal to have duplicate primary keys. <br/>

#### **How to install Clickhouse**

```shell
brew install clickhouse/clickhouse/clickhouse
```

#### **Start Clickhouse service**

```shell
brew services start clickhouse
```

#### **Enter Clickhouse CLI**

```shell
clickhouse client
```

#### **Create database**

```clickhouse
CREATE DATABASE IF NOT EXISTS learning
```

#### **Use created database**

```clickhouse
use learning
```

#### **Create table**

```clickhouse
create table messages (id UInt32, timestamp DateTime, message String) ENGINE = MergeTree PRIMARY KEY id
```

#### **Show tables**

```clickhouse
show tables
```

#### **Insert data into table**

```clickhouse
INSERT INTO messages VALUES (1, now(), 'Message #1'), (2, now(), 'Message #2'), (3, now(), 'Message #3')
```

#### **Drop table**

```clickhouse
drop table messages
```