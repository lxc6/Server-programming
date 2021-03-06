ES6

## ES6与javascript的区别？

* **`答：`**
* **`ES6是JS的语法，JS语法的ES6版本，`**
* **`JS是由dom，bom，ECMASCRIPT 组成的脚本编程语言`**

## 什么是块级作用域？举例说明？

* **`答：在{}中用let，const定义的变量，其作用域只能在{}内使用，该作用域为块级作用域`**

  ```js
  #  例子：
  {
      let a = 10;
      {
       let a = 1000;
      console.log(a)//结果为1000
  	}
      console.log(a)//结果为10
  }
  
  ```

  

## let-var-const

请回答下列代码中的console.log()语句的输出结果，并解释。

### 题1

```js
{
    let age = 18;
    console.log(age); // 18
}
console.log(age);

# 答：
# 输出结果为： 18  报错age未定义
# 因为let定义age变量在{}中，形成块级作用域，只作用于{}中，外部age没定义
```

### 题2

```js
for (let i = 0; i < 11; i++) {
    
}
console.log(i);  
# 答：
# 输出结果为：报错i未定义
# 小括号（）内部let定义变量i，形成隐藏块级作用域，循环体外部i没定义
```

### 题3

```js
for (var i = 0; i <= 9; i++) {
    
}
console.log(i);  
# 答：
# 输出结果为：10
# var定义的变量没有块级作用域
```

### 题4

```js
console.log(gender); 
let gender = '男'; 
# 答：
# 输出结果为：报错gender未初始化  
# let定义的变量没有变量提升
```

### 题5

```js
console.log(a); # 输出结果为：undefined
var a = 1; 
let b = 2;
let name = 'ok'
console.info(a,b)# 输出结果为： 1,2 
console.info(window.a)# 输出结果为：1
console.info(window.b)# 输出结果为：undefined
console.info(window.name)# 输出结果为：空
# 答：
# 输出结果为：undefined  1,2  1  undefined  空
# var定义的变量有变量提升，并且全局变量会附加到window对象的属性中,而let不会提升也不会附加
```



### 题6

```js
const  b = 1; 
b = 2;
console.log(b); 
# 答：
# 输出结果为：报错——常数变量赋值
# const定义的为常数变量，一旦定义不能再对其赋值
```



### 题7

```js
const  obj = {a:1}; 
obj = 2;
console.log(obj); 
# 答：
# 输出结果为：报错——常数变量赋值
# const定义的常量为复杂数据类型时，只能保正数据地址不被修改，不能保证其复杂数据内部的修改
# obj=2会改变数据地址 所以会报错
```



### 题8

```js
const  obj = {a:1}; 
obj.b = 2;
console.log(obj);
# 答：
# 输出结果为 {a: 1, b: 2}
# const定义的常量为复杂数据类型时，只能保正数据地址不被修改，不能保证其复杂数据内部的修改
# obj为一个对象 是复杂数据类型
```



### 题9

```js
const  obj = {a:1,b:[1]}; 
obj.b[2] = 2;
console.log(obj); 
# 答：
# 输出结果为 {a: 1, b:[1,空,2]}
# const定义的常量为复杂数据类型时，只能保正数据地址不被修改，不能保证其复杂数据内部的修改
# obj.b[2] = 2;是给obj对象中的b数组的下标为2的位置上赋值
```





## 数组解构赋值

### 题1

```js
let arr = [5, 9, 10];
let [a, b, c] = arr;
console.log(a, b, c); 
# 答：
# 输出结果为：5 9 10 
# 左边变量个数与右边数组数据个数 相等
```



### 题2

```js
let arr = [5, 9, 10];
let [a, b, c, d] = arr;
console.log(a, b, c, d); 
# 答：
# 输出结果为：5  9  10 undefined
# 左边变量个数大于右边数组数据个数 一次从左到右对应数据 多余的变量没有默认值所以为undefined
```

### 题3

```js
let arr = [5, 9, 10, 8, 3, 2];
let [, , a, , b] = arr; 
console.log(a, b); 
# 答：
# 输出结果为：10 3
# 空位占位 跳过不需要的值
```





### 题3

```js
let arr = ['zhangsan', 18, ['175cm', '65kg']];
// 如何让a的值是175cm,b的值是'zhangsan
// 请输入你的代码
# 答：
# 代码为： let[b,,[a]]

console.log(a, b); // 175cm 'zhangsan'
```



### 题4

```js
let arr = [1,2,3,4,5];
let [a, b, ...c] = arr; 
console.log(a, b, c); 
# 答：
# 输出结果为：1  2  [3,4,5]
# ...c 接收剩余的其他值，得到的c是一个数组
```





### 题5

```js
let arr = [1,2];
let [a=2,b,c=3] = arr; 
console.log(a, b, c); 
# 答：
# 输出结果为：1  2  3
# a默认值被数据替换，c没有数据保持默认值
```



### 题6

```javascript
var a = 1, b = 2;
// 写代码,实现互换a,b的值
# 答：
# 代码为： [a,b] = [b,a]

console.info(a,b); // 要求输出 2, 1
```



## 对象解构赋值

### 题1

```js
let { name, age,address='1' } = {age: 27, name: '阳明'};
console.log(name, age,address); 
# 答：
# 输出结果为：阳明 27 1
```

### 题2

```js
let {b, name:a} = {name: '王阳明'};
console.log(b, a, name);
# 答：
# {"b":b, "name":a} = {name: '王阳明'}
# 输出结果为：undefined 王阳明  ''   ??????????????
```

### 题3

```js
let { name='a', age,address='1' } = {};
console.log(name, age,address); 
# 答：
# 输出结果为：a undefined 1
```

### 题4

```js
let obj = {
    name: 'zhangsan',
    age: 22,
    dog: {
        name: '毛毛',
        age: 3
    }
};
// 下面写一句代码，把 zhangsan '毛毛' 解析出来
//  你的代码
# 答：
#代码为：let{name,dog:{name:name1}} = obj
console.log(name, name1); // zhangsan '毛毛'

```



### 题5

```js

let response = {
    data: ['a', 'b', 'c'],
    meta: {
        code: 200,
        msg: '获取数据成功'
    }
}
// 如何获取到 code 和 msg
// 你的代码
# 答：
#代码为：let{ meta:{code},data:[,d] } = response
console.log(code, d); // 200, 'b'
```



### 题6

```js
let obj = {name:'zs', age:20, gender:'男'};
let {age, ...a} = obj;
console.log(age, a);
# 答：
# 输出为：20 {name:'zs', gender:'男'};
# object  ...剩余值为一个对象
```



## 函数

给出如下代码的输出结果，并解释。

### 题1

```javascript
function f(a=1,b=2){
	console.log(a,b,a+b);
}
f(10)       # 10 2  12   a参数默认值被传入数据替换为10 ，b参数默认值不变
f(10,20)	# 10 20 30	 a参数默认值被传入数据替换为10 ，b参数默认值替换为20
f()			# 1  2  3    a参数默认值不变 ，b参数默认值不变
```

### 题2

```javascript
function f2(a=1,b){
	console.log(a,b,a+b);
}
f2(10)     # 10 undefined NAN
f2(10,20)  # 10 20 30
f2(,3) 	   # 报错
f2()	   # 1 undefined NAN
```

### 题3

```js
function f1({a=1,b=2}={}){
   console.log(a,b,a+b);
}
# 等同于 f1({"a":a=1,"b":b=2}={"a":undefined,b:undefined}){}
#       f1({a=1,b=1}){}
f1({a:10,b:20}) # 10 20 30
f1({a:20})		# 20 2 22
f1({c:1})		# 1 2 3    没有c ab使用默认值
f1()			# 1 2 3
```

### 题4

```js
function f2 (x,...y){
    console.log(x,y)
}
f2(1,2); 		# 1 [2]
f2(2,3,4);		# 2 [3,4]
# 函数的 ...  rest参数 多余数据组成标准数组
```

### 题5

```js
function f1 (x,y){
    console.log(x,y)
}
f1(1,2);    # 1 2
f1(2,3,4);  # 2 3
# 函数  实参个数大于形参 按顺序传参 多余实参数据省略
```



### 题6

用箭头函数对下列函数进行改写

```js
function f1(x){
	console.log(x)
}
# let f1 = x => console.log(x);

function f2(x,y){
	return x + y
}
# let f2 = (x,y) => x + y;

function f3(x,y){
	return {a:x,b:x+y}
}
# let f3 = (x,y) => {a:x,b:x+y}
```

### 题7

写出如下代码的输出，并解释原因。

```js
var name = 'a'; 
let obj = {
    name: 'b',
    f1 : () => {
        console.log(this);
        console.log(this.name); 
    },
    f2 : function(){
        console.log(this); 
        console.log(this.name); 
    }
};
obj.f1(); # 输出为: window  'a'  箭头函数的this不指对其向调用的对象，其this从外部（代码块外部）继承
obj.f2(); # 输出为: 整个obj{----}  'b' 
```

### 题8

写出如下代码的输出，并解释原因。

```js
var obj = {
    f1:()=>{
        console.log(this)
    },
    f2:function(){
        console.log(this)
    },
    f3:function(){
       var f = ()=>{ console.log(this) }
       return f 
    },
    f4:function(){
        setTimeout(function(){console.log(this)})
    },
    f5:function(){
        setTimeout(()=>{console.log(this)})
    },
    f6:()=>{
        setTimeout(()=>{console.log(this)})
    },
    f7:()=>{
        setTimeout(function(){console.log(this)})
    },
}

obj.f1();		# window
obj.f2();		# obj		
obj.f3()();		# obj	
obj.f4();		# 定时器内的函数是普通函数，它的this是window
obj.f5();		# 定时器内的函数是箭头函数，它的this由外层决赛
obj.f6();		# window
obj.f7();		# window
```



##  数组

### 题1

```JS
let arr1 = [1,2,3];
let arr2 = [...arr1];
console.log(arr2); 	#[1,2,3]  rest 三点方法实现浅拷贝
```



### 题2

```javascript
var arr0 = ['a','b'];
var arr1 = [1,2,3];
var arr2 = [4, ...arr1];
var arr3 = [..arr0 ,...arr1];
console.log(arr2,arr3);#[4,1,2,3]['a','b',1,2,3]  rest 三点方法实现浅数组拼接
```

### 题3

```javascript
var arr = [1,3,4,6];
// 使用Math.min求最小值
// var min = ?
# var min = Math.min(...arr)
console.info(min);// 1
```

### 题4

从一个复杂的对象数组中找出符合条件的对象。

```javascript
let data = [
    {id:2,name:'严嵩',age:15},
    {id:3,name:'徐阶',age:17},
    {id:4,name:'高拱',age:18},
    {id:1,name:'张居正',age:12},
]
// 使用find找出‘高拱’的age,注意使用箭头函数来简化代码

let result = 数组.find(function(item,index,self){ 
    //.... 
    // 如果满足查找的条件
    return true;
})
var rs = data.find(item=>item.name ==‘高拱’ );
# let age = data.find(function(item,index,self){if(item.name=='高拱') return ture})
# let age = data.find(item=>{return item.name=='高拱'})
# 最终为： let res = data.find(item=>item.name=='高拱') console.log(res.age)
```

### 题5

```javascript
let arr = [1,1,2,3,3];
// 一句代码实现数组去重
// let arr1 = ?
# let arr1 = [...new Set(arr)]
console.info(arr1); // [1,2,3]
```



