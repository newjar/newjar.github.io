---
title: "Basic Ruby Syntax"
layout: post
tag:
- Ruby
comments: true
author: nurulfajar
---

* Use :: only to reference constants(this includes classes and modules) and constructors (like Array() or Nokogiri::HTML()). Do not use :: for regular method invocation.

```ruby
# bad
SomeClass::some_method
some_object::some_method

# good
SomeClass.some_method
some_object.some_method
SomeModule::SomeClass::SOME_CONST
SomeModule::SomeClass()
```

* Use def with parentheses when there are parameters. Omit the parentheses when the method doesn't accept any parameters.

```ruby
# bad
def some_method()
  # body omitted
end

# good
def some_method
  # body omitted
end

# bad
def some_method_with_parameters param1, param2
  # body omitted
end

# good
def some_method_with_parameters(param1, param2)
  # body omitted
end
```
* Methods that have "keyword" status in Ruby:

```ruby
class Person
  # bad
  attr_reader(:name, :age)
  # good
  attr_reader :name, :age

  # body omitted
end
```

* Do not use then for multi-line if/unless

```ruby
# bad
if some_condition then
  # body omitted
end

# good
if some_condition
  # body omitted
end
```

[Learn More](https://github.com/bbatsov/ruby-style-guide#syntax).
