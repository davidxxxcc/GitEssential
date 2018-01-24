# How JavaScript works

## Execution context

Everything we declare in the global object will automatically get attach to windows object

![](https://lh3.googleusercontent.com/D7cR6iIiOoZkc3NDoourJD705617OssmElroF0YuYQB4J6r97SPn5mvsDI4OSObfT9rjtEjPeir8TZm-amiThyJOKa0liRRxSMD95yVuzfpzoUDY0P46LwC_KpoT-ODr_yHUiUMq)

## Execution stack

![](https://lh4.googleusercontent.com/10VcsYUzzyUb4JpQK74fWYiLHOfViUXUk9azcXO6k3hLohED8XwySQg9qDVHGxv3S4z2fhJYlIchIP8vTnrBpm8k1Lz_QdOhmfpfnoJs9x5GRh8IfC-5cp2z1Pvlv2eMAbfxI7ao)

## The execution context in detail

![](https://lh6.googleusercontent.com/GCO1JZMx30FbyFYMFyXq1K3ZoFGBvfp7I1R4Bqd0z7DjlRrK7_Cufi4NbvrR1tJ5VKkjfFBgyKbFJP_npTCg-gmTj5YXgisER-xg3nH4aTsPTQFvhGUaxjxF0mzxDzbFoXN1euQ2)

### The variable object

![](https://lh5.googleusercontent.com/Mr2SfS88TAVrlaJlaC4oLuiGLf2QD0xyxyAoMJv1_kvXuNiU2qB8qDTeQKteCsKKlz__6pqdv8oRBAhK-5aS-TXuXRzx5BOafS1Ldcjt6NA0bVQq0a61dSurVJfQ3a71ILjWFlEb)

### Code demo:

`calculateAge(1965); //work`

`function calculateAge(year) {`

`console.log(2016 - year);`

`}`

`calculateAge(1990); //work`

`retirement(1990); //not work`

`var retirement = function(year) {`

`console.log(65 - (2016 - year));`

`}`

`retirement(1990); //work`

`console.log(age); //not work`

`var age = 23;`

`console.log(age); //work`

`console.log(age);`

`var age = 23;`

`  
`

`function foo() {`

`console.log(age);`

`var age = 65;`

`console.log(age);`

`}`

`foo();`

`console.log(age);`

![](/assets/123)

## Scoping in JavaScript

![](/JavaScript/3)![](/assets/JS-2)![](/assets/JS-3)

## This

### ![](/assets/JS-4)Code demo:

`var john = {`

`name: 'John',`

`yearOfBirth: 1990,`

`calculateAge: function() {`

`console.log(this);`

`console.log(2016 - this.yearOfBirth);`

`  
`

`function innerFunction() {`

`console.log(this);`

`}`

`innerFunction();`

`}`

`}`

![](/assets/JS-5)

