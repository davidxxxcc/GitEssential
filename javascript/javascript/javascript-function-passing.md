## Function Passing![](/assets/js-20)![](/assets/js-21)

![](/assets/js-22)

## Funciton Returning functions

You can implement the function with following way, this code includes two steps

`interviewQuestion('teacher')('Mark')`

1. `interviewQustion('teacher')`

2. anonymous `function(name)`

![](/assets/js-23)

## IIFE \(Immediately Invoked Function Expression\)

Data privacy

Its all about variable scoping. Variables declared in the self executing function are, by default, only available to code within the self executing function. This allows code to be written without concern of how variables are named in other blocks of javascript code.

```
(function (){

var score = Math.random() * 10;
console.log(score >= 5);
})();

(function (goodLuck){
var score = Math.random() * 10;
console.log(score >= 5 - goodLuck);
})(5);
```

## Closures

**An inner function has always access to the variables and parameters of its outer function, even after the outer function has returned.**

```
function retirement(retirementAge) {
var a = ' years left until retirement.'; //Outer function
return function(yearOfBirth) {
    var age = 2016 - yearOfBirth; //Inner function
    console.log((retirementAge - age) + a);
    }
}


var retirementUS = retirement(66);
retirementUS(1990); //40 years left until retirement.
retirement(66)(1990); //40 years left until retirement.
```

## Method borrowing \(call, apply and bind\)

### call is to borrow function and set its own property

### apply is almost same as call while apply implement array variable

```
var john = {
name: 'John',
age: 26,
job: 'teacher',
presentation: function(style, timeOfDay) {
    if (style === 'formal') {
        console.log('Good ' + timeOfDay + ', Ladies and gentlemen! I\'m ' + this.name + ', I\'m a ' + this.job + ' and I\'m ' + this.age + 'years old.') ;    
    } else if (style === 'friendly') {
        console.log('Hey! What\'s up? I\'m ' + this.name + ', I\'m a ' + this.job + 'and I\'m ' + this.age + 'years old.');
    }
    }
};

var emily = {
name: 'Emily',
age: 35,
job: 'designer'
};

john.presentation('formal', 'morning');        //Good morning, Ladies and gentlemen! I'm John, I'm a teacher and I'm 26years old.

john.presentation.call(emily, 'friendly','afternoon');        //Hey! What's up? I'm Emily, I'm a designerand I'm 35years old.
```

### bind is borrow partial function

```
var johnFriendly = john.presentation.bind(john, 'friendly');  
johnFriendly('night');  //Hey! What's up? I'm John, I'm a teacherand I'm 26years old.
var emilyFormal = john.presentation.bind(emily,'formal');
emilyFormal('afternoon');   //Good afternoon, Ladies and gentlemen! I'm Emily, I'm a designer and I'm 35years old.
```



### 



