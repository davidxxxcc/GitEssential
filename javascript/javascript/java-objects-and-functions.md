![](/assets/js-8)![](/assets/js-9)![](/assets/js-10)

![](/assets/js-11)![](/assets/js-12)

## function constructor \(variable starts with capital letter\)

`var Person = function(name, yearOfBirth, job) {`

`this.name = name;`

`this.yearOfBirth = yearOfBirth;`

`this.job = job;`

`}`





創建 Foo 物件和設定 prototype 中的 x 和 calculate\(\)

`function Foo(y) {`

`  this.y = y;`

`}`

`Foo.prototype.x = 10;`

`Foo.prototype.calculate = function (z) {`

`  return this.x + this.y + z;`

`};`

通過 object Foo 的 constructor，創建 instance b:

`var b = new Foo(20);`

`b.calculate(30); // 60`

`console.log(`

`  b.__proto__ === Foo.prototype, // true`

`  b.__proto__.calculate === Foo.prototype.calculate // true`

`  b.__proto__.calculate === b.calculate, // true`

`  Foo === b.constructor, // true`

`  Foo === Foo.prototype.constructor, // true`

`);`





