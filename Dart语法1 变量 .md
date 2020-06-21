## 一个简单的Dart程序

```
<!--定义一个函数-->
printInteger(int aNumber){
    print('the number is $aNumber');
    <!-- 输出到控制台 -->
}

<!-- 应用从这里开始执行 -->
main(){
  var number = 42;        //声明并初始化一个变量 
  printInteger(number);   //调用函数
}

```
## 重要的概念 
学习dart时 应该基于以下事实和概念

- 任何保存在变量中的 都是一个```对象```  并且所有的对象都对应一个```类```的实例 无论是数字 函数 null 都是对象 对象都继承自```Object```类
- 尽管Dart是强类型 但是Dart可以推断类型 所以类型注释是可选的 
- Dart是支持泛型的 如 ```List<int>```（整数列表）或者```List<dynamic>```(任何类型的对象列表)
- Dart支持顶级函数 如 ```main()```  同样的函数绑定在类或对象上（分别是 ```静态函数```和```实例函数```）  以及支持函数内创建函数（```嵌套```或``` 局部函数```）
- 类似地 Dart支持顶级变量 同样变量绑定在类或对象上 （静态变量和实例变量） 实例变量有时称为字段或属性 
- 与Java不同 Dart没有关键字 "public" "protectd" 和 "private" 如果标识符以下划线（_）开头 则它相对于库是私有的
- 标识符 以字母或者下划线（_）开头 后跟任意字母和数字组合 
- Dart 语法中包含 ```表达式(expressions)(有运行时值) ``` 和 ```语句 (statements)(没有运行时值)``` 一条语句通常包含一个或多个表达式 相反表达式不能直接包含语句 
- Dart 工具提示两种类型问题  警告 和 错误  警告只是表明代码可能无法正常工作 但不会阻止代码执行  错误可能是编译时错误或者 运行时错误 编译错误会阻止代码运行 运行错误会在代码执行过程引发 [异常]

## 关键字 列表
dart 关键字列表 

|||||
---|---|---|---
abstract 2|	dynamic 2	| implements 2	| show 1
as 2	|else|	import 2|	static 2
assert|	enum|	in|	super
async 1	|export 2|	interface 2|	switch
await 3|	extends|	is	|sync 1
break|	external 2|	library 2|	this
case|	factory 2	|mixin 2|	throw
catch	|false|	new	|true
class	|final|	null|	try
const|	finally	|on 1	|typedef 2
continue|	for|	operator 2	|var
covariant 2|	Function 2|	part 2|	void
default|	get 2	|rethrow	|while
deferred 2|	hide 1|	return|	with
do	|if	|set 2|	yield 3

## 变量
```
var name = 'bob'
```
变量仅存储对象引用 这里的变量是 name 存储了一个String类型的对象引用 
name变量的类型被推断为String  但是也可以通过指定类型的方式 来改变变量的类型 
如果对象不限定为单个类型 可以指定为 对象类型 或 动态类型

```
dynamic name = 'bob'
```
另一种 显式声明 可以推断出类型 
```
String name = 'bob'
```
## 默认值 
未初始化的变量默认值是 ```null```  即使变量是数字  类型默认值也是 null 因为在Dart中 一切皆对象 数字类型 也不例外
```
int lineCount;
assert(lineCount == null)
```
## Final 和 Const 
使用过程中从来不会被改变的变量 可以使用 final 或 const   final变量的值 只能被设置一次 const 变量在编译时 就已经固定 （const 是隐式Final的类型） 最高级的final类型或者类变量在第一次使用时被初始化
```
final name = 'Bob';  //不做类型声明
final String nickname = 'Bobby'
name = 'Alice'  //Error 一个final变量只能被设置一次
```
const关键字不仅可以用于声明 还可以用来创建常量值 以及声明创建常量值的构造函数 任何变量都可以拥有常量值 
声明const的初始化表达式中 const可以被省略 
非final 非const的变量是可以被修改的 即使这些变量曾经引用过const值

## 内建类型 
Dart 支持以下的内建类型 
- Number
- String 
- Boolean
- List(也被称为 Array)
- Map
- Set
- Rune(用于在字符串中表示Unicode字符)
- Symbol

### Number
Dart的Number有两种类型 
- int
整数值不大于64位
- double 
64位（双精度）浮点数 
int double都是num的亚类型   num类型包括基本运算 + - / * 以及 abs() ceil() floor()等函数方法 