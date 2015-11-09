---
layout: post
title:  "Ruby Classes"
date:   2015-10-17 19:20:10
author: Joe Marion
---

Since Ruby is an object-oriented and along with objects there are classes. Classes are like outlines that objects are instantiated upon. For this example I will use the common car reference. If we examine a vehicle, there are characteristics that make up what a vehicle is. Wheels, fuel capacity, power, etc are all data members of the class Vehicle. Using data members within the class, you can identify different objects that are instances of that class. To continue the example if I were to have two vehicles, a Pathfinder, and a Tacoma these would both be considered objects in Ruby that are instances of the class Vehicle. Both vehicles have data memebers that are different that help differentiate the two.

<!--more-->



This can be taken even further becuase vehicles have different functions. They can drive, stop, turn, accelerate, etc. These functions that are built within a class can even further form the data members within the class Vehicle. A class would be described as characteristics and functions together that make up the object.

### Defining a Class

Classes typically start with an initial capitalized letter. For this example we are going to create a class called Die that will return a random number based on how many sides of a die is entered.

```ruby
class Die
end
```

Here we have just created an empty class that we will work on throughout this post. One important topic we should go over is the importance of variables within classes.


* Local: Local variables have the smallest scope out of the four types of variables. They are located within methods and are not available outside of the method. The syntax for local variables is typically a lowercase letter or an underscore.
* Instance. Instance variables are available accross methods for a particular instance or object. This is commonly seen within classes because an object that is an instance of a class can have access to the instance variables accross the entire range of the class within that object. (If this sounds confusing it will make more sense when we build Die) The syntax for an instance variable is @ before the variable name.
* Class: Class variables are available accross different objects that belongs to the class. It is a characteristic of the class. The syntax for a Class variable is @@ before the variable name.
* Global: Global variables are available accross classes. Class variables are available accross objects, but not classes. That is why you would use a global. Global variables syntax is the dollar sign $ before the variable name.


### Methods within classes

So far in our class Die we don't have anything put in. One thing that classes are capable of, are adding methods to the class. The first method should be to initialize it. This is typically the first method ran when creating a new object thats instance of the class.

```ruby
class Die
  def initialize(labels)
  @labels = labels
  raise ArgumentError.new('Please add sides to the die') if labels.length < 1
end
..
```

So far all this class is doing is initializing and taking in one argument and storing it within an instance variable called @labels. This is done because we want to access the variable throughout this class and not just within the initialize method. That's why we wouldn't just keep it a local variable. As you can see, classes also let you set parimeters that can raise arguments if something is wrong.

```ruby
class Die
  def initialize(labels)
    @labels = labels
    raise ArgumentError.new('Please add sides to the die') if labels.length < 1
  end

  def sides
    return @labels.length
end

  def roll
    return @labels[rand(@lavels.length)]
  end
end
```

Here is the rest of the class Die. Look over and review why it is important to use instance variables in this situation. A question to answer is, why wouldn't we just use global variables? Well.. If we did that we would not only have to remember every single time we created a variable, but it would also leave the program more susceptible to malicious attacks and inefficient running. Especially on a high-traffic website.