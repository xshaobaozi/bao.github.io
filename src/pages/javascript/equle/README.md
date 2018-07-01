## === 和 ===

关于 === 和 == ,在js里面 如果使用 == js会隐式调用转换方法把左右两边进行同类型的转换然后再比较

比如:
```javascript
    let a = 1;
    let b = '2';
    let c = 2;
    let d = 2;
    a == 2 // false
    d == 2 // true
    这里其实先调用了 a.String() 再和 2 进行比较

    b === c //false
    全等比较 不会进行转换
```