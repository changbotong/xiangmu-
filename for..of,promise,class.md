### 一、***for ...of***

```
作用:主要用于遍历迭代器,(数组,set和map对象,字符串,这些都是迭代器)
定义:for(item of 遍历的数组){}
```

### 二、***promise***

```html
1.promise是什么？
主要用于解决回调地狱的一种异步方法
2.三种状态，并且执行是不可逆的
进行中(padding),成功(fulfilled),失败(rejected)
3.promise抛出的api
.then()
.catch()
.all() //可以调用多个promise返回的数据 ;Promise.arr([fn(),fn1()])(是一个数组).then().catch()
.race() //只要有状态改变(无论是成功还是失败)，立马返回
.finally() //无论成功还是失败，都会执行
4.应用场景 :数据请求二次封装
5其他异步方案
async await (.then都可以用await来表示)
      思想:用同步的形式来编写异步代码
      async 默认返回promise
```

##### ***promise定义***

```js
function fn(flg){
    return new promise((resolve,reject)=>{
      resolve(数据)//正确数据
      reject(数据)//错误数据
    }) 
}
consoloe.log(fn())//返回的是一个对象
fn(true).then(res=>{
    res//获取正确数据
}).catch(error=>{
    error//获取错误数据
})
```

### ***三、class类***

***1 一堆名词***

```html
父类 : 基类
子类 : 派生类
封装 : 对一类功能的复用(有入参，出参)
继承 : 对已封装好的模块，进行二次封装
多态 : 在JS中体现不明显(多种状态)
原型链
原型 :prototype :相当于多个公用空间
面向对象 : 万物接对象 对象包括 ：属性和方法
             属性:特征，特性，手机:品牌、颜色、价格、产地、销量 （名词）
             方法 ：功能、打电话、发短信、娱乐、移动办公 （动词）
对象即实例 ： 通过类实例的具体个体
一个类能造出多个实例
```

***2 如何创建一个类***

```
通过构造函数
通过ES6类创建
类的第一个字母一般大写
```

通过ES5来创建 -- 通过function来模拟创建类

```js
function Person(name="默认值"){}   (放自己的)    
方法一般放在function的原型上(公共的放在原型)
Person.prototype.sleep = function(){}
Person.prototype.work = function(){}
Person.prototype.eat = function(){}

new Person()
```

通过ES6来创建 -- 通过function来模拟创建类

```js
class Person{
       //constructor相当于构造器
       constructor(name="默认值"){}
}
sleep(){}
work(){}
eat(){}
```



***3 如何继承一个类***

```
ES5
  1.原型链继承 (不能传参，但能继承方法)
  2.构造函数继承
   子类中通过call来实现属性的继承  父类名称.call(this//当前，属性名)
  3.组合继承
     原型链借用构造函数继承的组合
ES6
  extends配合super
  在子类名后加 extends 父类名
  将ES5中的   父类名称.call(this//当前，属性名)
    父类名称.call变为super  否则会报错
```



***4 如何实例化一个类***