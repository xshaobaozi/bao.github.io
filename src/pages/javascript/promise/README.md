## Promise

Promise是一种异步编程的解决方案，对于多个异步操作的调用 使用Promise组织代码可以避免函数的多层嵌套

### Promise基本用法

```javascript

   const promise  = new Promise((resolve, reject) => {
       API.getToken()
           .done(res => {
                resolve(res)
            })
            .fail(err => {
                reject(err)
            })
    })
    promise
        .then(res => {
            // done
        },err => {
            // fail
        })
        .catch(err => {
            // fail
        })
```
Promise.then(done, fail)
Promise.then接口两个参数 分别是成功回调和失败回调 对应resolve 和 reject
Promise.catch在运行错误或者没有写fail回调并且失败的时候会捕捉错误进入

then默认返回undefined
对于多个异步操作需要按顺序调用可以这样

```javascript

   const promise1  = new Promise((resolve, reject) => {
       API.getToken()
           .done(res => {
                resolve(res)
            })
            .fail(err => {
                reject(err)
            })
    })
    const promise2  = new Promise((resolve, reject) => {
       API.getUser()
           .done(res => {
                resolve(res)
            })
            .fail(err => {
                reject(err)
            })
    })
    promise1
        .then(res => {
            return promise2
        })
        .done(res => {
            // promise2 -> done
        })
        .catch(err => {
        })
```
运行完promise1后再调用promise2 把promise1的response 返回给promise2作为参数调用

### Promise.finally
Promise.finally不管promise状态如何 最后都会调用
finally不接受任何参数
```javascript
    promise
    .then(result => {···})
    .catch(error => {···})
    .finally(() => {···});
```

### Promise.all
```
   let promise_all = [
        promise1(),
        promise2(),
        promise3()
   ];
   Promise.all(promise_all)
   .then(res => {

    })
    .catch(err => {

        })
```

### Promise.race
