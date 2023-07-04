---
layout: post
title:  "after_create vs after_commit"
date:   2023-06-28 23:12:00 +0800
categories: Ruby on Rails
---

### after_create
Code will be executed before the record is being save. If error happen, rollback will occur.

### after_commit 
Code will be executed only after the record is being saved into database.

<br>

Tip: If you want to execute job and the job need to refer to the record, it is better to use `after_commit` to ensure the record is saved and job can search for that record.