# Ruby Language

It's much like python
- no semicolon
- no types

## I/O
for input we use
```ruby
gets 
```
lets the user input a line and returns it as a value to your program, This value includes the trailing line break. 


to not include the line break we use:
```ruby
gets.chomp 
```

to get a number we use:
```ruby
gets.to_i
```

to output something with a newline
```ruby
puts "Hello"
```

to output something without
```ruby
name = "Ramez"
print "Hello, #{name}"
```

## Arrays
to make an array
```ruby
arr = []
arr = Array.new(n, 0)
arr = (1..5).to_a  # => [1, 2, 3, 4, 5]
```

inserting element
```ruby
arr = [1, 2, 3]
arr << 4        # => [1, 2, 3, 4]
arr.push(5)     # => [1, 2, 3, 4, 5]

arr = [2, 3, 4]
arr.unshift(1)  # => [1, 2, 3, 4]

arr = [1, 2, 4]
arr.insert(2, 3)  # => [1, 2, 3, 4]  (index starts at 0)
```

removing element
```ruby
arr = [1, 2, 3, 4]
last = arr.pop    # => 4   (returns the removed element)
p arr             # => [1, 2, 3]
```

## Loops

times loop 
```ruby
5.times do |i|
  puts "Hello #{i}"  
end
# i goes from 0 to 4
```


for loop
```ruby
for i in 1..5
  puts i # 1 2 3 4 5
end
```

each loop
```ruby
arr = [10, 20, 30]
arr.each do |num|
  puts num
end

# with index
arr.each_with_index do |value, index|
  puts "#{index}: #{value}"
end
```

while loop
```ruby
i = 0
while i < 5
  puts i
  i += 1
end

```

range with step
```ruby
(1..5).step(1) do |i|
    puts i
end
```

## Functions 

Normal function

```ruby
def greet(name = "stranger")
  puts "Hello, #{name}!"
end

greet        # => Hello, stranger!
greet("Ali") # => Hello, Ali!
```

Handling args
```ruby
def sum_all(*numbers)
  numbers.sum
end

puts sum_all(1, 2, 3, 4)  # => 10
```

## Data Structures
### Hash
```ruby
h = { "name" => "Ramez", "age" => 21 }
h["name"]         # => "Ramez"
h[:city] = "Cairo"

h = { name: "Ramez", age: 21 }
```

### Set
```ruby
require 'set'
s = Set.new([1, 2, 2, 3])  # => #<Set: {1, 2, 3}>
s.add(4)
```

## Classes

```ruby
class Person
    attr_accessor :name  # creates getter and setter methods

  def initialize(name)
    @name = name
  end
  
  def greet
    puts "Hello, I'm #{@name}!"
  end
end

p1 = Person.new("Ramez")
p1.greet  # => Hello, I'm Ramez!

p1.name = "Ja"
p1.greet # => Hello, I'm Ja!
```

Class Method
```ruby
class MathHelper
  def self.square(x)
    x * x
  end
end

puts MathHelper.square(5)  # => 25
```
Inhertence
```ruby
class Animal
  def speak
    puts "Some sound"
  end
end

class Dog < Animal
  def speak
    puts "Woof!"
  end
end

Dog.new.speak  # => Woof!
```