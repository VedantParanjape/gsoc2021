---
layout: page
title: "/language-specification"
permalink: /language/
---

# Language Specification for PRU

* Language Name: SimpPRU
* Statically typed language
* TAB or 4 spaces for indentation

# Primitive data types: 
* `int`
* `bool`

# Binary operators
* `/` divide
* `*` multiply
* `+` plus
* `-` minus     
# Unary operators
* `&` unary and
* `|` unary or
* `~` unary not
# logical operator
* `and` logical and
* `or` logical or
* `not` logical not
operator precedence, as arranged

# Arithmetic operations
* `int` and `float` can be operated together, `int` will be promoted to float
* `bool` cannot be operated with anything other than `bool`
* `bool` only supports unary operators
# Variable assignment
* `<data_type> <identifier> := <value>`     
{% highlight python %}int value := 34{% endhighlight %}

# if elif else loop        
{% highlight python %}  
if <condition_to_be_evaluated>:
    <do something>
elif <condition_to_be_evaluated>:
    <do something>
else:
    <do something>
{% endhighlight %}

# for loop
{% highlight python %}
for <identifier>, <condition>, <action to loop completion>:
    <do something>
{% endhighlight %}

# functions
{% highlight python %}
<return type> <function name> (<data type> variable name, ...):
    <do something>

int add(int a, int b):
    return a + b
{% endhighlight %}
* Each functions must always return something, since void data type is not included

# Register Access
{% highlight python %}
bool read_register(register_name, bit_to_be_read)
bool write_register(register_name, bit_to_be_written, bool value_to_be_written)
{% endhighlight %}
