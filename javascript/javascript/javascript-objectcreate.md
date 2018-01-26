## The other way to create object in JavaScript is object.create

The difference between object.create and the function constructor pattern is that

* Object.create builds and object that inherits directly from the one that we passed into the first argument
* Function constructor newly created object inherits from the constructor's protoptye property.

![](/assets/js-15)

