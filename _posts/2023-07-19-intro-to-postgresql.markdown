---
layout: post
title: "Intro to PostgreSQL"
date: 2023-07-19 21:53:00 +0800
categories: PostgreSQL
---

#### **Connect to PostgreSQL CLI**
```shell
psql
```

#### **Display databases**

```shell
\l
```

#### **Create database**

```shell
create database dvdrental;
```

#### **Load installed database [dvdrental](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip){:target="_blank"}**

```shell
# this is in shell, not in psql cli
pg_restore -U <username> -d dvdrental <location>/dvdrental
```

#### **Connect to database**

```shell
\c dvdrental
```

#### **Display all tables in database**

```shell
\dt
```

#### **Query table**

```shell
selct * from customer;
```

#### **Quit PostgreSQL CLI**

```shell
\q
```