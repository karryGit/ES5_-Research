### 判断数据是否是数组

```	
    var arr = [1,2,3,4,5]
    console.log(Array.isArray(arr));//true
```

***

### 判断数组中的值所在下标

```	
    var arr = [1,2,3,4,5]
    console.log(arr.indexOf(2));//1
```

***

### 指定数组或字符串值最后出现的位置

```
   var arr = [1,2,3,4,5,4]
   console.log(arr.lastIndexOf(4));
```

***

### 对数组的每个元素进行一个条件检查

```
 var arr1 = "Charles,Mark,Bill,Vincent,William,Joseph".split(",");
    arr1.every(function (item,index) {
        console.log(item.length < 3);//false
        //判断数组中每个值的长度是否小于3
    })
```

***

### 判断数组有没有符合条件的元素

```
    var arr1 = "Charles,Mark,Bill,Vincent,William,Joseph".split(",");
    console.log(arr1.some(
            function (item, index) {
                return item.length < 5;
                //判断数组中有没有符合条件长度小于5的数值
                }
            )
    ); //true
```

### forEach()

```

等同于for循环
var arr = [-1,0, 1, 2, 3, 4];
第一种: 回调函数            
 参数1:数组的值
 参数2:数组值的下标
 参数3:数组本身
arr.forEach(function (t, i, arr) {
    console.log(t, i, arr);
});
```

***



### map()

```
map()
处理数组中的每个元素,产生一个新的数组
//回调函数中传递的参数代表数组里的值而不是下标
//回调函数返回值 ,否则映射的新数组都是undefined
var result = arr.map(function(item){
    return item + "$";
});
console.log(result);
```

***

### filter()

```
//过滤数组,然后产生新数组
//回调函数中传递的参数代表数组里的值而不是下标
//返回值一般是布尔值true/false, 也可以是弱==true/false的值
var result = arr.filter(function (item) {
    return item > 3;
});
console.log(result);
```

***

### reduce()

```
//迭代递归,类似for循环处理数组
//回调函数 有4个参数
// 参数1:迭代之前的值
// 参数2:迭代当前的值
// 参数3:数组的下标,默认0
// 参数4:数组
//reduce有参数2 initialValue可选,默认值为数组第一个值
var result = arr.reduce(function(previous, current, index, array){
    return previous + current;
},1);
console.log(result);
```

***

### reduceRight()

```
//从数组的末尾开始
var result = arr.reduce(function(previous, current, index, array){
    return previous - current;
},1);
console.log(result);
//过程如下
// previous = initialValue = 1, current = 4      index=5
// previous = (1 - 4) =  -3, current = 3         index=4
// previous = (-3 - 3) =  -6, current = 2        index=3
// previous = (-6 - 2) =  -8, current = 1        index=2
// previous = (-8 - 1) =  -9, current = 0        index=1
// previous = (-9 - 0) =  -9, current = -1       index=0
// previous = (-9 - -1) =  -8, current = undefined(退出)
```

***

### ES5和ES6数组遍历方法详解

```
在ES5中常用的10种数组遍历方法:
1、原始的for循环语句
2、Array.prototype.forEach数组对象内置方法
3、Array.prototype.map数组对象内置方法
4、Array.prototype.filter数组对象内置方法
5、Array.prototype.reduce数组对象内置方法
6、Array.prototype.some数组对象内置方法
7、Array.prototype.every数组对象内置方法
8、Array.prototype.indexOf数组对象内置方法
9、Array.prototype.lastIndexOf数组对象内置方法
10、for...in循环语句
```

***

### ES6中新增加了一种

```
1.for...of循环语句
```



#### 数组内置方法Array.prototype.reduce

```
var a = [1,2,3];
var b = a.reduce(function (count, value,key,arry) {
  console.log(count);   // 结果依次为0，1，3
  console.log(value);   // 结果依次为1，2，3
  console.log(key);     // 结果依次为0，1，2
  console.log(arry)     // 三次结果都为[1,2,3]
  return count + value;
},0);
console.log(a);         // 结果为[ 1, 2, 3 ]
console.log(b)          // 结果为6
代码解读：reduce的不同之处在于累加，和其他几个内置方法不同的地方，它的第二个参数不是this对象，而是初始累加值（如果不设置的话数组会乱掉），而且回调函数的的个数也不同，比其他的多了一个，而且还在在开始的多加了一个参数，第一个参数记录的是上一次循环的累加值，下面写一个reduce循环实现例子供大家参考：
```

