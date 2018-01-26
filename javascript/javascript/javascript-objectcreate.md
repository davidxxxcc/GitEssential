## The other way to create object in JavaScript is object.create

![](/assets/js-16)

The difference between object.create and the function constructor pattern is that

* With object.create\(\) we build a new object that inherits from the object that we passed into the first argument, so basically we can use any object as a prototype
* While with the function consctructor we can only inherit from the constructor prototype property.
* object.create allows us to implement a really complex inheritant structure in an easier way

Object.create\(\):

![](/assets/js-18)

Constructor:

![](/assets/js-19)

