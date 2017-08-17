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

