## What Is Self in Ruby & How to Use It?

If you’re learning Ruby you may find the use of the “self” keyword very confusing.<br/>

How does it work?<br/>

What is self, exactly?<br/>

###

self is a Ruby keyword that gives you access to the current object.<br/>

Here’s an example:<br/>

If your code is inside an instance method, self is an instance of that class. In other words, <br/>
self is an object.

### let' see an example

"def coffee<br/>
  puts self<br/>
end<br/>
coffee"<br/>
 main<br/>

This code defines & calls a coffee method which prints the value of self.<br/>

Why is self useful?<br/>

by example<br/>

"class Example <br/>
  def do_something<br/>
    banana = "variable"<br/>
    puts banana<br/>
    puts self.banana<br/>
  end<br/>
  def banana<br/>
    "method"<br/>
  end<br/>
end"<br/>

Example.new.do_something<br/>
 "variable"  => puts banana <br/>
 "method"    => puts self.banana <br/>

Here we have a banana local variable, inside the do_something method, but we also have a banana method.<br/>

A local variable takes priority.<br/>

That’s why we need to use self here if we want to call the banana method, instead of printing the value of the banana variable.<br/>
