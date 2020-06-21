对于Dart而言 函数也是对象  并且有它的类型 Function   这也意味着函数可以被赋值给变量或者作为参数传递给其他函数 也可以把Dart类的实例当中方法来调用 
函数实现示例
```
bool isNoble(int atomicNumber){
  return _nobleGases[atomicNumber] != null;
}
```
如果函数中只有一句表达式 则可以使用简写语法 
```
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
```
```=>expr```语法是 ```{return expr;}```的简写    也就是箭头函数的写法
函数有两种参数类型   required和optional  required类型在参数最前面 随后是 optional类型参数  
命名的可选参数也可以标记为 '@required'

## 可选参数 
可选参数可以是命名参数 或者 位置参数  但是 一个参数只能选择其中一种方式 修饰

### 命名可选参数 
调用函数时 可以使用指定命名参数 paramName:value
```
enableFlags(bold: true,hidden: false);
```
定义函数 是使用```{param1,param2,param3,...}```来指定命名参数 例如
```
void enableFLags({bool bold, bool  hidden}){...}
```
