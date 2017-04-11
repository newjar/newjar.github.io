---
title: "Ruby Source Code Layout"
layout: post
tag:
- Ruby
comments: true
author: nurulfajar
---

* Use UTF-8 as the Source file encoding.
* Use to **spaces** per indentation level (aka soft tabs). No hard tabs.

 ```ruby
# bad - four spaces
def some_method
    do_something
end

# good
def some_method
  do_something
end
  ```

 * Don't use ; to separate statements and expressions. As a corollary—use one expression per line.

 ```ruby
# bad
puts 'foobar'; # superflous semicolon

puts 'foo'; puts 'bar' # two expressions on the same line

# good
puts 'foobar'

puts 'foo'
puts 'bar'

puts 'foo', 'bar' # this applies to puts in particular
   ```

 * Prefer a single-line format for class definitions with no body.

 ```ruby
# bad
class FooErro < StandError
end

# okish
class FooError < StandardError; end

# good
FooError = Class.new(StandardError)
   ```

 * No space inside range literals.

```ruby
# bad
1 .. 3
'a' ... 'z'

# good
1..3
'a'...'z'
```

* Don't use several empty lines in a row

```ruby
# bad - It has two empty lines.
some_method


some_method

# good
some_method

some_method
```
[Learn More](https://github.com/bbatsov/ruby-style-guide#source-code-layout).
