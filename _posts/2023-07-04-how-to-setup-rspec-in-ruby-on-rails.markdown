---
layout: post
title:  "How to setup RSpec in Ruby on Rails"
date:   2023-07-04 00:00:00 +0800
categories: Ruby on Rails, RSpec
---

#### Add RSpec, Factory Bot, Faker and Database Cleaner gem to Gemfile

```ruby
# Gemfile

group :development, :test do
  gem "rspec-rails"
  gem "factory_bot_rails"
  gem "faker"
end

# Note:
# 1. Usually only use 'database_cleaner-active_record' in Rails
# 2. If got any other ORM can use 'database_cleaner' eg. sequel, mongo, redis
# 3. No need to load in development because you always want some data to play with in development
group :test do
  gem "database_cleaner-active_record"
end
```

#### Setup Factory Bot and use Faker

```ruby
# 0. Add below configuration inside spec/rails_helper.rb
config.include FactoryBot::Syntax::Methods

# 1. Create factories folder inside spec folder
mkdir spec/factories

# 2. Create model file, eg. User model with name and email column
touch spec/factories/user.rb

# 3. Inside spec/factories/user.rb
FactoryBot.define do
  factory :user do
    name { Faker::FunnyName.name }
    # unique method is to ensure the generated value always unique
    email { Faker::Internet.unique.email }
  end
end
```

#### Setup Database Cleaner

```ruby
# Add database cleaner strategy inside spec/rails_helper.rb
config.before(:suite) do
  DatabaseCleaner.strategy = :transaction
  DatabaseCleaner.clean_with(:truncation)
end

config.around(:each) do |example|
  DatabaseCleaner.cleaning do
    example.run
  end
end
```