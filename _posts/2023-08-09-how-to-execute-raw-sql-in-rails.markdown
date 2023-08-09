---
layout: post
title:  "How to execute raw SQL in Rails"
date:   2023-08-09 23:14:00 +0800
categories: SQL, Ruby on Rails
---

Execute raw SQL directly from ActiveRecord::Base or ApplicationRecord inherited from ActiveRecord::Base
```ruby
sql = 'SELECT * from tables;'

results = ActiveRecord::Base.connection.execute(sql)
results = ApplicationRecord.connection.execute(sql)

# results will contain PG::Result object, eg:
#<PG::Result:0x00007f9eb76637c8 status=PGRES_TUPLES_OK ntuples=1 nfields=7 cmd_tuples=1>
```

Access results
```ruby
results.each do |r|
  puts r
end
```

<br>

**Reference**

[How do you manually execute SQL commands in Ruby On Rails using NuoDB](https://stackoverflow.com/questions/22752777/how-do-you-manually-execute-sql-commands-in-ruby-on-rails-using-nuodb){:target="_blank"}<br>
[Executing raw sql against multiple data bases](https://stackoverflow.com/questions/42954158/executing-raw-sql-against-multiple-data-bases){:target="_blank"}<br>
[Understanding PG Result object](https://blog.kiprosh.com/understanding-pg-result-object/){:target="_blank"}

