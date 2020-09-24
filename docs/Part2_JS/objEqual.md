# 判断两个对象完全相同

```js
let obj1 = {
    id:1,
    name:'a',
    like:{
        value:'value1',
        title:'aaa',
    }
}
let obj2 = {
    id:1,
    name:'a',
    like:{
        title:'aaa',
        value:'value1'
    }
}
```

```js
/*
* 测试：
* objEqual(obj1,obj2) // true
*/
objEqual(obj1,obj2){
    var o1 = obj1 instanceof Object;
    var o2 = obj2 instanceof Object;
    /* 判断不是对象 */
    if(!o1 || !o2){
        return obj1 === obj2;
    }
    /* 判断key数量是否相同 */
    if(Object.keys(obj1).length !== Object.keys(obj2).length){
        return false;
    }
    for(var attr in obj1){
        var t1 = obj1[attr] instanceof Object;
        var t2 = obj2[attr] instanceof Object;
        if(t1 && t2){
            return diff(obj1[attr],obj2[attr]);
        }else if(obj1[attr] !== obj2[attr]){
            return false;
        }
    }
    return true;
}
```
