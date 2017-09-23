# 作用域和闭包

1.词法作用域
2.函数作用域
3.块级作用域
4.变量提升
5.作用域闭包

1.词法作用域

词法作用域也被称为静态作用域，即是在定义词法阶段所确定的作用域，词法作用域关注在何处声明，来决定定义的词法的作用域。不同于动态作用域，动态作用域是在程序运行时确定的。

```js
function foo(a){
    var b = a = 2;

    function bar(c){
        console.log(a, b, c);
    }

    bar(b*3);
}

foo(2); //2,4,12
```
其中，做外层作用域只有一个标识符foo，foo作用域内有a、bar、b三个标识符，bar作用域内有c一个标识符，每一个作用域都由定义的时候决定，不会在后面改变。

2.函数作用域
JavaScript时给予函数作用域的，即属于某个函数的全部变量都可以在整个函数的范围内使用及复用