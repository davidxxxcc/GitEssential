## 構造函數\(Constructor\)

在Javascript语言中，用来从原型对象\(e.g. function DOG\)生成一个实例对象\(e.g. dogA\)。但是，Javascript没有"类"，怎么来表示原型对象呢？

new命令后面跟的不是类，而是构造函数，举例来说，现在有一个叫做DOG的构造函数，表示狗对象的原型。

`function DOG(name){`

`this.name = name;`

`}`

对这个构造函数使用new，就会生成一个狗对象的实例。

`var dogA = new DOG('大毛');`

`alert(dogA.name); // 大毛`

## Prototype屬性

用构造函数生成实例对象，有一个缺点，那就是**无法共享属性和方法**。**如果在構造函數裡設定共享的屬性和方法，每個實體都會有共用的屬性跟方法，就會佔用了多餘的空間來做重複的事情**，因此，Javascript引入一個prototype的屬性來解決這個問題。

这个属性包含一个对象（以下简称"prototype对象"），所有实例对象需要共享的属性和方法，都放在这个对象里面；那些不需要共享的属性和方法，就放在构造函数里面。

实例对象一旦创建，将自动引用prototype对象的属性和方法。也就是说，实例对象的属性和方法，分成两种，一种是本地的，另一种是引用的。

现在，species属性放在prototype对象里，是两个实例对象共享的。只要修改了prototype对象，就会同时影响到两个实例对象。

`function DOG(name){`

`this.name = name;`

`}`

`DOG.prototype = { species : '犬科' };`

`var dogA = new DOG('大毛');`

`var dogB = new DOG('二毛');`

`alert(dogA.species); // 犬科`

`alert(dogB.species); // 犬科`

## 總結:

**你有一個叫做DOG的函數，就可以把DOG當作 constructor，利用var obj = new DOG\(\)來 new 出一個DOG的 instance，並且可以在DOG.prototype上面加上你想讓所有 instance 共享的屬性或是方法。**



順帶一提，每一個 prototype 都會有一個叫做constructor的屬性，例如說Person.prototype.constructor，而這個屬性就會指向構造函數。Person.prototype的構造函數是什麼？當然就是Person囉。

![](/assets/js-14)



參考資料

[http://www.ruanyifeng.com/blog/2011/06/designing\_ideas\_of\_inheritance\_mechanism\_in\_javascript.html](http://www.ruanyifeng.com/blog/2011/06/designing_ideas_of_inheritance_mechanism_in_javascript.html)

[https://blog.techbridge.cc/2017/04/22/javascript-prototype/](https://blog.techbridge.cc/2017/04/22/javascript-prototype/)

## Another way to set constrcutor:

**function constructor \(variable starts with capital letter\)**

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

## 原型鍊**\(Prototype chain\)**

正如結果所示, b 物件繼承了 Foo\(\) 的屬性和方法\(method\). “Foo.prototype” 的內建方法 Foo.prototype.constructor 自動化地為 Foo\(\) 創造構建方法.  
Instances “b” 透過 constructor 把自身的 \_\_protot\_\_ 委任\(delegation\)到 Foo Object 的 prototype:

![](/assets/js-13)

![](blob:file:///bccb5ad5-7f7d-4558-a7a2-75904196481f)

![](blob:file:///1077cbd0-a5c1-4208-afa4-7021297e4c93)

