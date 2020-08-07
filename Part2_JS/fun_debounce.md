# 函数防抖
```js
/**
* 函数防抖
* @param {func} 函数
* @param {delay} 防抖间隔时间
*/
debounce(func, delay = 500) {
    let timer;
    return function(...args) {
        if (timer) {
            clearTimeout(timer);
        }
        timer = setTimeout(() => {
            func.apply(this, args);
        }, delay);
    };
}
```

