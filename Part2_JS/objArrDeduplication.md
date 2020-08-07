# 对象数组去重

```js
var arr = [
    {id:1,name:'aa'},
    {id:2,name:'bb'},
    {id:3,name:'aa'},
    {id:1,name:'bb'},
    {id:2,name:'bb'}
]
```

### 根据某个唯一标识去重
```js
/**
* 对象数组去重
* @param {objArr} 对象数组 [{},{},...]
* @param {objKey} 对象去重依据的key值
* 
* 测试：
* objArrDeduplication(arr,'name') //[{id: 1, name: "aa"},{id: 2, name: "bb"}]
* objArrDeduplication(arr,'id') //[{id: 1, name: "aa"},{id: 2, name: "bb"},{id: 3, name: "aa"}]
*/
objArrDeduplication(objArr,objKey) {
    let obj = {},resultArr = []
    resultArr = objArr.reduce (function(item,next){
        obj[next[objKey]] ? '' : obj[next[objKey]]  = true && item.push(next)
        return item;
    },[])
    return resultArr;
}
```
