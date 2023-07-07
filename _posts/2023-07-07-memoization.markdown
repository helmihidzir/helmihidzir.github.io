---
layout: post
title:  "Memoization"
date:   2023-07-07 23:53:00 +0800
categories: Ruby on Rails
---


```ruby
def abc
  @abc ||= begin 
    puts 'processing...'
    5555
  end
end 

abc
# processing...
# => 5555

abc
# => 5555
```