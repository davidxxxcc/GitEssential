## Function Passing![](/assets/js-20)![](/assets/js-21)

![](/assets/js-22)

## Funciton Returning functions

You can implement the function with following way, this code includes two steps

`interviewQuestion('teacher')('Mark')`

1. `interviewQustion('teacher')`

2. anonymous `function(name)`

![](/assets/js-23)

## IIFE \(Immediately Invoked Function Expression\)

data privacy

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



