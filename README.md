# ES6
ES6的常用知识点

## let
- 用来声明变量用，只在let命令所在的代码块内有效。
> 面对switch case 语句 在case代码块内的let作用域就不受case的控制。因为switch只有一个作用块，千万不要以为每一个case是一个作用块。
```
var name = "stepday";
switch(name){
   case "stepday":
      let foo;
   break;
   case "FED":
      let foo;//报错 提示foo已经被定义
   break;
}
```
> 全局定义的let变量，通过window无法访问到
```
ES5中 通过var和function申明的变量会归结到window的属性也就是全局变量
ES6中 通过let、const、class、import声明的变量是不会归结到window下的，进行了分离和脱钩处理
以上的局别一定要注意。

let a = 100;
function fn(){
   console.log(this.a); //undefined
}
fu()
```

> let的作用域可限制在大括号、ifelse、for、switch之内 不存在变量提升
> for循环有一个特别之处，就是设置循环变量的那部分是一个父作用域，而循环体内部是一个单独的子作用域，代码片段如下所示：
```
for (let i = 0; i < 3; i++) {
  let i = 'abc';
  console.log(i);
}
// abc
// abc
// abc
```
- 输出了三个abc，循环变量i和内部变量i不在同一个作用域，不然会出现报错。

