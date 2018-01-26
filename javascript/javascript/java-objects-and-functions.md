![](/assets/js-8)![](/assets/js-9)![](/assets/js-10)

![](/assets/js-11)![](/assets/js-12)

这个属性包含一个对象（以下简称"prototype对象"），所有实例对象需要共享的属性和方法，都放在这个对象里面；那些不需要共享的属性和方法，就放在构造函数里面。

实例对象一旦创建，将自动引用prototype对象的属性和方法。也就是说，实例对象的属性和方法，分成两种，一种是本地的，另一种是引用的。

參考資料

http://www.ruanyifeng.com/blog/2011/06/designing\_ideas\_of\_inheritance\_mechanism\_in\_javascript.html



## function constructor \(variable starts with capital letter\)

`var Person = function(name, yearOfBirth, job) {`

`this.name = name;`

`this.yearOfBirth = yearOfBirth;`

`this.job = job;`

`}`

創建 Foo 物件和設定 prototype 中的 x 和 calculate\(\)

`function Foo(y) {`

`this.y = y;`

`}`

`Foo.prototype.x = 10;`

`Foo.prototype.calculate = function (z) {`

`return this.x + this.y + z;`

`};`

通過 object Foo 的 constructor，創建 instance b:

`var b = new Foo(20);`

`b.calculate(30); // 60`

`console.log(`

`b.__proto__ === Foo.prototype, // true`

`b.__proto__.calculate === Foo.prototype.calculate // true`

`b.__proto__.calculate === b.calculate, // true`

`Foo === b.constructor, // true`

`Foo === Foo.prototype.constructor, // true`

`);`

正如結果所示, b 物件繼承了 Foo\(\) 的屬性和方法\(method\). “Foo.prototype” 的內建方法 Foo.prototype.constructor 自動化地為 Foo\(\) 創造構建方法.  
Instances “b” 透過 constructor 把自身的 \_\_protot\_\_ 委任\(delegation\)到 Foo Object 的 prototype:

![](/assets/js-13)

