---
layout: post
title:  "Arrays and Hashes"
date:   2015-10-02 20:37:53 +0800
author: Joe Marion
---

What is the difference between an array and a hash? First off, we have to define what an array and a hash is.

> "Hashes are like arrays where they can be recalled, but instead of using integer-indexes they use keys."

<!--more-->

### Arrays

Ruby doc defines an array as ordered, integer-indexed collections of any object. What does that mean? It means that an array can store multiple objects within itself to be recalled later. An array can hold values that are Integers, Floats, strings.. even other arrays. Here is an example of an array:

```
sample_array = [1, "two", 3.0]
```

In this example a new array is set up using Ruby's shorthand that includes an integer, a string, and a float. (This is the same example that Ruby doc's uses). Each of these three objects are stored with an index number that can be used to recall their value. The thing about arrays is that they start at index 0. This is important because human nature tends to start counting with one and that can lead to problems down the road.

Now, what does index 0 mean? It means that each value is assigned an integer index number. In the example above we have the objects 1, two, and 3.0 with indexes of 0, 1, and 2 respectively. In Ruby you can recall these values like so:

```
sample_array[0] => 1
sample_array[1] => "two"
sample_array[2] => 3.0
```

See how that can be confusing? Once you get used to indexing with 0 it gets easy, but someone just starting out may forget.

Now this is all fine and dandy, but what if you have an array with 1000 integers and you have find if there is a specific value stored within your array? You would have to waste time either creating a seperate method to search or manual search the arrays yourself. This can become time consuming, especially on a larger scale. Here is where we get to hashes.</p>

### Hashes

A hash is similar to an array except that it is stored with a key value pair. First, let's look at an example of a hash to let the code do some of the explaining.


```
sample_hash = Hash.new
sample_hash["Dog"] = "Animal that is loyal"
sample_hash["Fish"] = "Animal that swims"
sample_hash["Person"] = "Animal(?) that is confusing"
```


Hashes are like arrays where they can be recalled, but instead of using integer-indexes they use keys. This can be helpful because if we want to see if the description of a person was included in the hash we could just recall the key for person and it will display whether it is included or not. If this were an array it would be difficult to remember what specific index that Person was included in or if it was included at all.
