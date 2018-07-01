## this

关于this方法其实网上已经有很多的介绍了，this其实就是当前执行函数的上下文

### 改编this的方法

1. call
2. bind
3. apply

```
    const a = {
        test: function() {
            console.log(this.aa)
        },
        aa: 1
    };
    const b = {
        aa: 2
    };

    a.test() // 1
    a.test.call(b) // 2
    a.test.bind(b);
    a.test() // 2
    a.test.apply(b, []) // 2
```
call、bind、apply都能改变this指向 区别只是参数不同 emmm使用还是有点区别的

### 箭头函数

```
    for(let i = 0; i < 10; i++) {
        setTimeout(() => {
            console.log(i)
        }, 0)
    }
    // 0,1,2,3,4,5...
```
