---
layout: post
title:  "JavaScript Prototypes vs Ruby Classes"
date:   2015-10-22 09:40:17
author: Joe Marion
---

Looking at the two languages it is easy to compare Javascript's prototypes to Ruby's classes. They may be working to accomplish the same thing, but their approach is what makes them different.

<!--more-->

First, let's look at what Ruby's classes are and what they are in charge of doing. They create new objects, and define the blueprint from which the manufactored objects behaves. Classes are Objects interact with other objects by providing a collection of methods that match the concerns the other objects manage. Objects then implement those methods by manipulating thier internal, hidden-state. Ruby's methods encapsulate their inner state so that working within Ruby presents an interface for   uerying and updating object behaviour through methods. <a href="http://raganwald.com/2014/01/19/prototypes-are-not-classes.html">Raganwald</a> had some interesting points on this topic explaining the differences.

In JavaScript, their objects do not have formal classes. They are created with a constructor and in JavaScript any function can be a constructor. An instance constructor is a function that was invoked with the new operator.

#### A common way you may see constructors written in JavaScript coming from a class-based language may look like:

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
  this.getFull = function () {
      return this.make + " " + this.family;
  };
}
```

This might not be the best approach because using the this keyword it is bound. Using constructors like this is much more like creating a static method. In the code above, you are providing that method to only that particular instance. Functions can, for the most part, be treated just like objects in JavaScript.

Here is where prototypes come into play. Prototypes will allow methods to be easily defined to instances of the instance in a way that saves memory. The method will be applied to the prototype of the object, so it is only stored once in the memory. This is helpful because objects coming from the same constructor point to one common object. All instances will have access to that method.

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
}
Car.prototype.getFull = function () {
      return this.make + " " + this.family;
  };
  ```

The difference between this prototype and the previous constructor is that any method attached with the this keyword will get re-declared for every new instance we create, which could heavily impact the memory usage of the application. Now with objects in the prototype it saves a considerable amount of memory not re-declaring for every new instance.

Back to the differences between classes and prototypes, a class can be an object, but it has special properties and methods.