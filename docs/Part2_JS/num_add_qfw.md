# 数值增加千分位符

```js
/**
* 数字加千位符
* @param {num} 数字
* @param {precision} 保留的小数位数
*
* 测试:
* console.log(thousandsFormat(569875.206, 2))   // 569,875.21
* console.log(thousandsFormat(569875.206, 0))   // 569,875
* console.log(thousandsFormat('569875.206', 6))   // 569,875.206000
* console.log(thousandsFormat('sd222', 2))   // sd222
* console.log(thousandsFormat('', 2))   // ''
* console.log(thousandsFormat('2019年')); // 2019年
* console.log(thousandsFormat('2019-6-8')); //2019-6-8
*/
thousandsFormat(num, precision = 0) {
    let _num = num
    if (typeof _num == 'string' && !_num.trim()) {
        return ''
    }
    _num = isNaN(Number(_num)) ? _num : parseFloat(_num);
    _num = (_num.toFixed ? _num.toFixed(precision) : _num) + '';
    if (!_num.includes('.')) _num += '.';
    return _num.replace(/(\d)(?=(\d{3})+\.)/g, function ($0, $1) {
        return $1 + ',';
    }).replace(/\.$/, '');
}
```

