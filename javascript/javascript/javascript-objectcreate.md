The difference between object.create and the function constructor pattern is that

* Object.create builds and object that inherits directly from the one that we passed into the first argument
* Function constructor newly created object inherits from the constructor's protoptye property.

`// Object.create`

`var personProto = {`

`calculateAge: function() {`

`console.log(2016 - this.yearOfBirth);`

`}`

`}`



`var john = Object.create(personProto);`

`john.name = 'John';`

`john.yearOfBirth - 1990;`

`john.job = 'teacher';`



`var jane = Object.create(personProto,`

`{`

`name: {value: 'Jane'},`

`yearOfBirth: { value: 1969 },`

`job: { value: 'designer' }`

`});`

