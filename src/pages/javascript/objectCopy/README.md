## 深|浅拷贝
深拷贝和浅拷贝的区别就是拷贝完后是不是独立的一份
浅拷贝内存里面指向不变
深拷贝是独立的一份指引

### 浅拷贝
```javascript
   const obj1 = {a: 1, b: 2};
   const obj2 = obj1;
   obj2.a = 2;
   obj1.a // 2
```

### 深拷贝
```javascript
   const obj1 = {a: 1, b: 2};
   const obj2 = JSON.parse(JSON.stringify(obj1))
   obj2.a = 2;
   obj1.a // 1

   const obj2 = Object.assign({}, obj1);
   obj2.a = 3;
   obj1.a // 1
```
以上是一层的拷贝 多层需要加些判断和递归操作=。=