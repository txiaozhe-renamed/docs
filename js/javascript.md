#### 基本语法

* 赋值

  ```javascript
  var x = 1; // ‘;’ 可选
  var a = 1; var b = 2; // 一行代码包含两个语句时必须加‘;’, 但不推荐一行写多个语句
  ```

* 字符串

  ```javascript
  'hello world'; // 也可用双引号
  ```

* 语句块

  ```javascript
  if(true) {
    x = 1;
    y = 2;
    z = 3;
  }
  ```

* 注释

  ```javascript
  // 这是行注释
  console.log('hello world');

  /* 从这里是块注释
  仍然是块注释
  块注释结束 */
  ```

#### 数据类型和变量

JavaScript中定义了以下几种类型

* Number

  JavaScript 不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：

  ```javascript
  123; // 整数123
  0.456; // 浮点数
  1.2345e3; // 科学计数法表示的浮点数
  -99; // 负数
  NaN; // 表示Not a Number, 当无法计算结果时用NaN表示
  Infinity; // 表示无限大，当数值超过了JavaScript 所能表示的最大值时表示为Infinity
  ```

  Number 能做四则运算，规则和数学一致：

  ```javascript
  1 + 2; // 3
  (1 + 2) * 5 / 2; // 7.5
  2 / 0; // Infinity
  0 / 0; // NaN
  10 % 3; // 求余，结果为1
  10.5 % 3; // 1.5
  ```

* String

  字符串是以单引号`'` 或 `"` 包含的任意文本，如`'ABC'` 、`"xyz"` 等

* Boolean

  布尔值用 `true` 和 `false` 表示

  ```javascript
  true; // 这是一个true值
  false; // 这是一个false值
  2 > 1; // 这是一个true值
  2 >= 3; // 这是一个false值
  ```

  `&& ` : 与运算

  ```javascript
  true && true; // 这个&&语句计算结果为true
  true && false; // 这个&&语句计算结果为false
  false && true && false; // 这个&&语句计算结果为false
  ```
  `|| ` : 或运算

  ```javascript
  false || false; // 这个||语句计算结果为false
  true || false; // 这个||语句计算结果为true
  false || true || false; // 这个||语句计算结果为true
  ```

  `!` : 非运算

  ```javascript
  ! true; // 结果为false
  ! false; // 结果为true
  ! (2 > 5); // 结果为true
  ```

  boolean 值通常用在条件判断中， 如：

  ```javascript
  var age = 15;
  if (age >= 18) {
      alert('adult');
  } else {
      alert('teenager');
  }
  ```

  比较运算符：

  通过运算符左右两边的运算可以得出一个布尔值：

  ```javascript
  2 > 5; // false 
  5 >= 2; // true
  7 == 7; // true
  false == 0; // true 
  false === 0; // false
  ```

  `==` 和 `===` :

  `==` : 会自动转化类型再做比较

  `===` : 不会自动转化类型，比较时先比较类型，若类型不一致则返回false，若类型一致再比较值，因为这种差异，建议一般情况下使用 `===` 而不是 `==`

* null 和 undefined

  `null` 表示一个空的值，和 `0` 或者 `''` 不一样，0 是一个数值，`''` 表示一个长度为0的字符串，而`null` 表示 空

  `undefined` 表示值未定义。事实上和`null` 区别不大，大多数情况下使用 `null`

* 数组

  JavaScript数组可以包含任意的数据类型

  ```javascript
  [1, 2, 3.14, 'hello', null, true]; // 元素之间用 ‘,’ 分隔
  ```

  另一种实现数组的方式是通过 `Array()` 函数实现：

  ```javascript
  new Array(1, 2, 3); // 创建数组[1, 2, 3]
  ```

  数组的元素通过索引来访问，索引的起始值为0：

  ```javascript
  var arr = [1, 2, 3.14, 'hello', null, true];
  arr[0]; // 1
  arr[3]; // hello
  arr[5]; // true
  arr[6]; // 索引超出了范围，返回undefined
  ```

* 对象

  JavaScript的对象是由一组键-值对组成的无序集合：

  ```javascript
  var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null
  };
  ```

  用 `对象.属性名` 的方式获取对象的属性：

  ```javascript
  person.name; // Bob
  person.zipcode; // null
  ```

* 变量

  变量名可以用除JavaScript关键字如if、while等之外的大小写英文、数字、$、和 _ 的组合，且不能用数字开头。声明一个变量用 var 语句

  以下都是合法的变量命名：

  ```javascript
  var a;
  var $b = 1;
  var s = "ooo";
  var answer = true;
  var _t = null;
  ```

  static 模式

  JavaScript中可以不使用 var 进行变量声明，此时变量就自动被声明为全局变量：

  ```javascript
  i = 10; // i 是全局变量，此时容易造成错误，不推荐这样写，在后续的ECMA标准中引入strict模式，强制通过var进行变量声明，使用strict模式的方法是在JavaScript代码的第一行写上 'use strict';
  ```

#### 字符串

字符串使用 `''` 或 `""` 包含，若 `'` 本身也要作为一个字符，则也用 `"" ` 包含，若字符串中既包含`'` 又包含 `"` 则可以用转义符 `\` 来标识：

```javascript
'I\'m \"OK\"!'; // 标识的字符串是 I'm "OK"!
```

转义字符可以表示很多含义：

```javascript
\n  换行
\t  制表符
\\  表示字符\
```

ascii 字符可以以 `\x##` 的方式表示：

```javascript
'\x41'; // 等同于 'A'
```

还可以用`\u####` 表示一个Unicode 字符：

```javascript
'\u4e2d\u6587'; // 等同于 '中文'
```

多行字符串

ES6标准新增了一种多行字符串的表示方法，用 `` 表示：

```javascript
`这是一个
 多行字符串`;
```

#### 数组

获取数组长度

```javascript
var arr = [1, 2, 3, 'hello', 1.5, null]
arr.length; // 6
```

直接给数组的length赋新值会导致数组大小的变化：

```javascript
var arr = [1, 2, 3];
arr.length // 3
arr.length = 6;
arr; // [1, 2, 3, undefined, undefined, undefined]
arr.length = 2;
arr; // [1, 2]
```

数组可以通过索引把对应的元素改成新的值，且当索引超过了数组范围，同样会引起数组大小的变化

```javascript
var arr = [1, 2, 3];
arr[5] = 'x'
arr; // arr 变为 [1, 2, 3, undefined, undefined, 'x']
```

* indexOf

  与String类似，数组也可以通过indexOf() 来搜索一个指定元素的位置：

  ```javascript
  var arr = [1, 2, 3, 3, '4', 'x'];
  arr.indexOf(1); // 0
  arr.indexOf(3); // 2 有相同的元素时返回第一次找到的位置索引
  arr.indexOf(5); // 没有找到，则返回-1
  ```

* slice

  截取数组的部分元素并返回一个新的数组

  ```javascript
  var arr = ['a', 'b', 'c', 'd', 'e', 'f', 'g'];
  arr.slice(0, 3); // ['a', 'b', 'c'] 从索引0到索引3但不包括3
  arr.slice(3); // ['d', 'e', 'f', 'g'] 从索引3开始到结束
  ```

  slice() 的起止参数包括开始索引，不包括结束索引，若不传入参数则截取整个数组，利用这个特点可以复制数组：

  ```javascript
  var arr = ['a', 'b', 'c'];
  var aCopy = arr.slice();
  aCopy; // ['a', 'b', 'c']
  aCopy === arr; // false, 注意，复制生成的数组和原数组并不相等
  ```

* push、pop

  `push()` 向数组末尾添加元素，`pop()` 则把数组最后一个元素删掉

  ```javascript
  var arr = [1, 2];
  arr.push('a', 'b'); // 4  注意，这里并不是返回新数组，而是返回新数组长度
  arr; // [1, 2, 'a', 'b']
  arr.pop(); // b 返回被删除的元素
  var arr1 = [];
  arr1.pop(); // undefined 对空数组执行pop() 操作会返回undefined，而不是报错
  ```

* unshift、shift

  `unshift() ` 向数组的头部添加元素，而 `shift()` 则是把数组的第一个元素删除

  ```javascript
  var arr = [1, 2];
  arr.unshift('a', 'b'); // 返回数组的新长度 4
  arr; // ['a', 'b', 1, 2]
  arr.shift(); // 'a' 返回被删除的元素
  ```

* sort

  `sort() ` 对当前的数组进行排序，会直接修改当前的元素位置

  ```javascript
  var arr = ['b', 'a', 'c'];
  arr.sort();
  arr; // ['a', 'b', 'c']
  ```

* reverse

  `reverse() ` 可以把整个数组前后反转：

  ```javascript
  var arr = ['one', 'tow', 'three'];
  arr.reverse();
  arr; // ['three', 'two', 'one']
  ```

* splice

  `splice() ` 可以从指定的索引开始删除若干元素，也可以再从该位置添加若干元素：

  ```javascript
  var arr = ['microsoft', 'apple', 'yahoo'];
  arr.splice(2, 1, 'google', 'facebook'); // ['yahoo] 返回删除的元素
  arr; // ['microsoft', 'apple', 'google', 'facebook']
  arr.splice(2, 1); // 只删除，不添加, ['google']
  arr; // ['microsoft', 'apple', 'facebook']
  arr.splice(2, 0, 'google'); // 只添加，不删除
  arr; // ['microsoft', 'apple', 'google', 'facebook']
  ```

* concat

  `concat ` 把当前数组和另一个数组连接起来并返回一个新的数组

  ```javascript
  var arr = ['a', 'b', 'c'];
  var added = arr.concat([1, 2, 3]);
  added; // ['a', 'b', 'c', 1, 2, 3]
  arr; // ['a', 'b', 'c'] 操作并不会影响原数组
  arr.concat(1, 2, [3, 4]); // ['a', 'b', 'c', 1, 2, 3, 4] concat() 可以接收任意个参数和数组，并自动把数组拆开添加到新的数组里
  ```

* join

  `join() ` 把数组中每个元素都用指定的字符串连接起来，并返回连接后的字符串

  ```javascript
  var arr = [1, 2, 3];
  arr.join('-'); // 1-2-3 若数组中的元素不是字符串则自动转换为字符串后再连接
  ```

* 多维数组

  ```javascript
  var arr = [[1, 2, 3], [400, 500, 600], '-'];
  ```


数组的迭代：

```javascript
var arr = [1, 2, 3, 4, 5];
```

* forEach() 让数组中的每一项做一件事

  ```javascript
  arr.forEach(function(ele) {
    console.log(ele); // 一次输出 1, 2, 3, 4, 5
  })
  ```

* map() 让数组中每一项进行某种计算并返回一个新数组

  ```javascript
  var a = arr.map(function(ele) {
    return 2 * ele;
  })
  console.log(a); // [2, 4, 6, 8, 10]
  ```

* filter() 筛选出数组中符合条件的项组成新数组

  ```javascript
  var a = arr.filter(function(ele) {
    return ele >= 3;
  })
  console.log(a); // [3, 4, 5]
  ```

* reduce() 让数组中的前项和后项进行某种计算并累计最终值

  ```javascript
  var a = arr.reduce(function(prev, next) {
    return prev + next;
  })
  console.log(a); // 15   1 + 2 + 3 + 4 + 5
  ```

* every() 检查数组中是否每一项都符合条件

  ```javascript
  var a = arr.every(function() {
    return item > 0;
  })
  console.log(a); // true 所有元素都满足条件才返回true
  ```

* some() 检查数组中是否有某些项符合条件

  ```javascript
  var a = arr.some(function() {
    return item > 3;
  })
  console.log(a); // true 只要满足一个就返回true
  ```

#### 对象

JavaScript的对象是一种无序的集合数据类型，由若干键值对组成

```javascript
var obj = {
  name: "hello",
  age: 20
}
```

如上所示，JavaScript用一个`{}` 表示一个对象，键值对以 `xxx.xxx` 表示，用`,` 隔开，最后一个键值对不需要逗号，可以通过`xxx.xxx` 来读取对象的属性：

```javascript
obj.name; // hello
obj.age; // 20
```

 可以使用unicode 中的所有字符表示属性名，当属性名不是一个有效的变量时需用 `''` 包含：

```javascript
var obj = {
  name: 'hello',
  '年龄': 20
}
obj['年龄']; // 20 访问这样的属性时必须用 [] 包含
obj.name; // hello
obj['name']; // hello 也可以用 [] 的方式访问具有有效的变量名的属性
obj.age; // undefined
```

JavaScript是动态类型的，因此可以自由地给一个对象添加或删除属性：

```javascript
var obj = {
  name: "hello"
}
obj.age; // undefined
obj.age = 20; // 添加一个属性
obj.age; // 20
delete obj.age; // 删除一个属性
obj.age; // undefined
delete obj.sex; // 删除一个不存在的属性也不会报错
```

使用 `in` 操作符检查是否拥有某属性：

```javascript
var obj = {
  name: "hello"
}
'name' in obj; //true
'age' in obj; // false
```

当一个属性是继承得到的，用 `in ` 检查时也为`true`:

```javascript
'toString' in obj; // true 因为toString 被定义在 object中，而所有对象在原型链中最终都指向 object, 所以obj也拥有 toString 属性
```

可以用 `hasOwnProperty()`方法判断一个属性是自身拥有的还是继承得到的

```javascript
var obj = {
  name: 'hello'
}
obj.hasOwnProperty('name'); // true
obj.hasOwnProperty('toString'); // false
```

#### 条件判断

使用`if() {...} else {...}`来进行条件判断，当只需判断一次时 `else ` 可省略，多个条件时也可多加 `else`

```javascript
var age = 20;
if(age >= 18) {
  console.log('adult');
} else {
  console.log('teenager');
}
```

#### 循环

`for ` 循环：

```javascript
var x = 0;
for(var i = 1; i <= 10000; i++) {
  x = x + i;
}
x; // 50005000
```

用 `for ` 遍历数组：

```javascript
var arr = [1, 2, 3, 4, 5, 6, 7];
for(var i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
```

`for` 循环的3个条件可以省略，但必须有 `break` 退出循环，否则就是死循环：

```javascript
var x = 0;
for(;;) {
  if(x > 100) {
    break; // 退出循环
  }
  x++;
}
```

`for ... in` 可以把一个对象的所有属性一次循环出来：

```javascript
var o = {
    name: 'hello',
    age: 20,
    city: 'hangzhou'
};
for (var key in o) {
    console.log(key); // 'name', 'age', 'city' 此时也可以调用hasOwnProperty() 过滤掉继承的属性
}
```

数组也是可以这样操作的：

```javascript
var a = ['A', 'B', 'C'];
for (var i in a) {
    alert(i); // '0', '1', '2'
    alert(a[i]); // 'A', 'B', 'C'
}
// 注意for ... in 对数组循环得到的是 string 而不是 number
```

`while` 循环：

```javascript
var x = 0;
var n = 99;
while (n > 0) {
    x = x + n;
    n = n - 2;
}
x; // 2500
```

`do ... while` 循环：

```javascript
var n = 0;
do {
    n = n + 1;
} while (n < 100);
n; // 100
```

#### 函数

定义函数：

第一种方式

```javascript
function abs(x) { // function 指出这是一个函数定义，abs是函数名称，(x) 列出函数的参数，多个参数以 , 分离
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}
```

第二种方式

```javascript
var abs = function (x) {
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}; // 这里加一个 ; 表示赋值语句结束
```

`function (x) {}` 是一个匿名函数，没有函数名，但这个匿名函数被赋值给变量 `abs` ，所以通过 `abs` 就可以调用该函数

调用函数

```javascript
abs(10); // 10
abs(-9); // 9
abs(-1, 'hello', '2'); // 1 JavaScript允许传入的参数与定义的参数个数不一致
```

也可以对参数进行检查

```javascript
function abs(x) {
    if (typeof x !== 'number') {
        throw 'Not a number';
    }
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}
```

arguments

arguments 指向当前函数调用者传入的所有参数，类似于数组但不是数组

```javascript
function foo(x) {
    console.log(x); // 10
    for (var i = 0; i < arguments.length; i++) {
        console.log(arguments[i]); // 10, 20, 30
    }
}
foo(10, 20, 30); // 即使函数定义的参数比传入的参数少甚至未定义参数，依然可以通过 arguments 获取所有参数
```

可以用arguments 检查参数个数

```javascript
function fun(a, b) {
  if(arguments.length !== 2) {
    throw '参数错误！'
  }
}
```

#### 作用域

如果在函数内部声明一个变量，则该变量的作用域为整个函数体，函数体外不能引用该变量：

```javascript
'use strict';

function foo() {
    var x = 1;
    x = x + 1;
}

function fun() {
    var x = 2;
    x = 2 * x;
}

x = x + 2; // ReferenceError! 无法在函数体外引用变量x，且不同的函数内的变量相互独立，无论参数名是否相同
```

JavaScript函数可以嵌套，此时内部函数可以访问外部函数的变量，反之则不行

```javascript
'use strict';

function foo() {
    var x = 1;
    function bar() {
        var y = x + 1; // bar可以访问foo的变量x
    }
    var z = y + 1; // ReferenceError! foo不可以访问bar的变量y
}
```

JavaScript的函数在查找变量时从自身函数定义开始从“内”向“外”查找。如果内部函数定义了与外部函数重名的变量，则内部函数的变量将“屏蔽”外部函数的变量

```javascript
'use strict';

function foo() {
    var x = 1;
    function bar() {
        var x = 'A';
        console.log(x); // A
    }
    console.log(x); // 1
    bar();
}
```

变量提升

JavaScript的函数定义会先扫描整个函数体的语句，把所有申明的变量“提升”到函数顶部：

```javascript
'use strict';

function foo() {
    var x = 'Hello, ' + y;
    console.log(x); // Hello, undefined
    var y = 'Bob';
}

foo(); // 结果并不报错，而是输出undefined，因为JavaScript引擎只提升了变量y的声明，而未提升变量y的赋值，因此是undefined
```

上述代码对于JavaScript引擎来说相当于

```javascript
function foo() {
    var y; // 提升变量y的申明
    var x = 'Hello, ' + y;
    alert(x);
    y = 'Bob';
}
```

> 因此在函数内部定义变量时建议先把所有变量在函数开始部分进行声明。

全局作用域

不在任何函数内定义的变量就拥有全局作用域，实际上JavaScript拥有一个全局对象 `window` ，全局作用域的变量会绑定到 `window` 上

```javascript
'use strict';

var course = 'hello world';
console.log(course); // hello world
console.log(window.course); // hello world
```

命名空间

全局变量会绑定到 `window` 上，不同的JavaScript变量如果使用了相同的全局变量或定义了相同的顶层函数都会造成命名冲突，避免这种冲突的方式就是将所有变量和函数绑定到一个全局变量中

```javascript
// 唯一的全局变量
var APP = {};

// 其他变量:
APP.name = 'myapp';
APP.version = 1.0;

// 其他函数:
APP.foo = function () {
    return 'foo';
};
```

局部作用域

由于JavaScript的作用域是函数作用域，因此在一些语句块中无法定义具有局部作用域的变量

```javascript
'use strict';

function foo() {
    for (var i = 0; i < 100; i++) {
        //
    }
    i += 100; // 仍然可以引用变量i
}
```

#### 方法

在一个对象中绑定的函数，成为这个对象的方法：

```javascript
var obj = {
  name: 'hello',
  age: 20,
  sayHello: function() {
    console.log("hello world");
  }
}

obj.sayHello; // function obj.sayHello()
obj.sayHello(); // hello world
```

在方法中的 `this` 变量是绑定到当前对象的，因此可以通过 `this.name ` 获取对象属性

**bind()** 、**apply()**、**call()**

这三个函数都可以用来改变函数内部 `this` 的指向

```javascript
var obj = {
	name: "hello"
}

function log(age, sex) {
	console.log(this.name + " " + age + " " + sex);
}

var log1 = log.bind(obj); // bind 函数返回了一个函数
log1('20', 'girl'); // hello 20 girl

log.apply(obj, ['20', 'boy']); // hello 20 boy 参数需要通过数组传入

log.call(obj, '21', 'boy'); // hello 21 boy 用法和apply() 一样，但不需要用数组的形式传入参数
```

#### 闭包

闭包就是把函数作为返回值

```javascript
function lazySum(a, b) {
  var sum = function() {
    return a + b; // 内部函数可以应用外部函数传入的参数
  }
  return sum;
}

var f1 = lazySum(1, 2)；
console.log(f1()); // 3 
var f2 = lazeSum(1, 2);
f1 === f2; // false
```

用闭包实现私有变量

```javascript
'use strict';

function create_counter(initial) {
    var x = initial || 0; // ||会检查initial，当initial存在时x = initial，否则为0
    return {
        inc: function () {
            x += 1;
            return x;
        }
    }
}
```

```javascript
var c1 = create_counter();
c1.inc(); // 1
c1.inc(); // 2
c1.inc(); // 3

var c2 = create_counter(10);
c2.inc(); // 11
c2.inc(); // 12
c2.inc(); // 13
```

在返回的对象中实现了一个闭包，该闭包携带了局部变量`x`，并且从外部代码无法访问到变量`x`。也就是说，闭包就是携带状态的函数，并且它的状态可以完全对外隐藏起来。

#### 标准对象

在JavaScript中，一切都是对象，用 `typeof` 获取对象的类型：

```javascript
typeof 123; // 'number'
typeof NaN; // 'number'
typeof 'str'; // 'string'
typeof true; // 'boolean'
typeof undefined; // 'undefined'
typeof Math.abs; // 'function'
typeof null; // 'object' 注意null和undefined是object类型的
typeof []; // 'object'
typeof {}; // 'object'
```

除了这些类型，JavaScript还提供了包装对象，相当于java中的 int 和 Integer：

```javascript
var n = new Number(123); // 
typeof n; // object 虽然看上去和原来的值一样且显示值也一样，但其实类型已经变成了object
var b = new Boolean(true); // true
var s = new String('hello'); // 'str'
// 一般情况下不建议使用这种包装类型
```

`Number()`、`Boolean ` 和 `String()`被当做普通函数，把任何类型的数据转换为 `number`、`boolean` 和 `string `类型

```javascript
var n = Number('123'); // 123
typeof n; // 'number'

var b = Boolean('true'); // true
typeof b; // 'boolean'

var b2 = Boolean('false'); // true! 'false'字符串转换结果为true！因为它是非空字符串！
var b3 = Boolean(''); // false

var s = String(123.45); // '123.45'
typeof s; // 'string'
```

#### Date

JavaScript 中 `Date` 用来表示日期和时间

获取系统时间：

```javascript
var now = new Date();
now; // Wed Jun 24 2015 19:49:22 GMT+0800 (CST)
now.getFullYear(); // 2015, 年份
now.getMonth(); // 5, 月份，注意月份范围是0~11，5表示六月
now.getDate(); // 24, 表示24号
now.getDay(); // 3, 表示星期三
now.getHours(); // 19, 24小时制
now.getMinutes(); // 49, 分钟
now.getSeconds(); // 22, 秒
now.getMilliseconds(); // 875, 毫秒数
now.getTime(); // 1435146562875, 以number形式表示的时间戳
```

创建指定日期和时间的Date 对象：

```javascript
var d = new Date(2015, 5, 19, 20, 15, 30, 123);
d; // Fri Jun 19 2015 20:15:30 GMT+0800 (CST)
```

也可以通过解析一个符合ISO 8601格式的字符串来创建Date对象：

```javascript
var d = Date.parse('2015-06-24T19:49:22.875+08:00');
d; // 1435146562875 返回一个时间戳
```

> 时间戳是一个自增的整数，表示从1970年1月1日零时整的GMT时区开始的那一刻到现在的毫秒数，假设浏览器所在电脑的时间是准确的，那么世界上无论哪个时区的电脑此刻产生的时间戳数字都是一样的，因此，时间戳可以精确地表示一个时刻，与时区无关

把时间戳转化为一个Date对象

```javascript
var d = new Date(1435146562875);
d; // Wed Jun 24 2015 19:49:22 GMT+0800 (CST)
```

时区

Date 所表示的时间总是按浏览器所在时区显示的，但可以显示本地时间或调整后的UTC时间：

```javascript
var d = new Date(1435146562875);
d.toLocaleString(); // '2015/6/24 下午7:49:22'，转化为本地时间（北京时区+8:00），显示的字符串与操作系统设定的格式有关
d.toUTCString(); // 'Wed, 24 Jun 2015 11:49:22 GMT'，UTC时间，与本地时间相差8小时
```

#### 正则表达式

正则表达式是一种用来匹配字符串的工具，是用一种描述性的语言来给字符串定义一个规则，凡是符合规则的字符串则认为它匹配了，否则认为该字符串是不合法的

JavaScript中匹配字符串的方法1：

直接通过 `/正则表达式/` 写出来

```javascript
var re1 = /ABC\-001/;
re1; // /ABC\-001/
```

JavaScript中匹配字符串的方法2：

通过 `new RegExp('正则表达式') ` 创建一个RegExp对象

```javascript
var re2 = new RegExp('ABC\\-001'); // 两个 \ 实际上是一个 \，在这里写两个是为了转义
re2; // /ABC\-001/
```

用 `test()`  方法对给定的字符串进行检查
```javascript
var re = /^\d{3}\-\d{3,8}$/;
re.test('010-12345'); // true
re.test('010-1234x'); // false
re.test('010 12345'); // false
```

切分字符串：

```javascript
// 用字符串的切分函数无法识别连续的空格
'a b   c'.split(' '); // ['a', 'b', '', '', 'c']
// 用正则表达式则可以识别连续空格
'a b   c'.split(/\s+/); // ['a', 'b', 'c']
```

分组

```javascript
var re = /^(\d{3})-(\d{3,8})$/;  //分别定义了两个组，可以直接从匹配的字符串中提取出区号和本地号码，用exec提取出子串
re.exec('010-12345'); // ['010-12345', '010', '12345'] 匹配成功后返回一个数组
re.exec('010 12345'); // null 匹配失败时返回null
```

全局搜索

```javascript
var r1 = /test/g;
// 等价于:
var r2 = new RegExp('test', 'g'); // g 表示全局匹配
```

全局匹配可以多次执行 `exec()` 方法来搜索一个匹配的字符串，指定 `g` 标志后，正则表达式会更新 `lastIndex` 属性，表示上次匹配得到的最后索引：

```javascript
var s = 'JavaScript, VBScript, JScript and ECMAScript';
var re=/[a-zA-Z]+Script/g;

// 使用全局匹配:
re.exec(s); // ['JavaScript']
re.lastIndex; // 10

re.exec(s); // ['VBScript']
re.lastIndex; // 20

re.exec(s); // ['JScript']
re.lastIndex; // 29

re.exec(s); // ['ECMAScript']
re.lastIndex; // 44

re.exec(s); // null，直到结束仍没有匹配到
```

#### JSON

json 实际上是JavaScript的一个子集，json 所包含的数据类型有：number、boolean、string、null、array、object，且其中的字符串必须使用双引号 `""`，Object的键也必须用双引号 `""`

把JavaScript对象序列化为JSON 字符串：

```javascript
var obj = {
    name: 'hello',
    age: 20
};

JSON.stringify(obj); // '{"name":"hello","age":20}'
// 加入一些参数可以使json按照缩进输出
JSON.stringify(obj, null, '  ');
// {
//  "name":"hello",
//  "age":20
// }
```

通过反序列化把JSON字符串转化为JavaScript对象：

```javascript
JSON.Parse('{"name":"hello","age":20}'); // {name: 'hello', age: 20}
```

