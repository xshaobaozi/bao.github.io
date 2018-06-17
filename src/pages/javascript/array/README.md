## Array

### 数组的复制

   数组的复制是浅复制
```javascript

   const a = [1, 2];
   const b = a;

   b[o] = 3;
   a // a -> [3, 2]
```

### Array.from

from方法可以吧类数组对象和可遍历对象转变为真正的数组

```javascript
   let dom = document.querySelectorAll('div');
   Array.from(dom).map(item => item)

```

通过这种方法可以遍历NodeList，部分浏览器Nodelist.forEach方法不兼容 需要转换为真正数组

### Array.of

把一组数值转变为数组

```javascript
   Array.of('', '', '') // ['', '', '']
```

### Array.find 和 Array.findIndex

find 可以找到Array中第一个匹配的元素并返回
```javascript
   let a = [1, 2, 3, 4].find(item => item === 2)
   //a = 2

```
findIndex 找到第一个匹配的元素的索引
```javascript
   let a = [1, 2, 3, 4].find(item => item === 2)
   //a = 1
```

### Array.forEach
forEach用于遍历数组，没有返回值

### Array.map
map用于遍历数组 返回本身