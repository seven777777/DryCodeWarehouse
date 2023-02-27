# 色值转RGBA
```js
/**
* color=>rgba
* @param {color} 色值
* @param {opacity} 透明度
*
* 测试:
* console.log(colorToRGBA('00B4B6',0.2)); //rgba(0,180,182,0.2)
*/
colorToRGBA(color, opacity) {
    let _color
    if (color.substr(0, 1) == "#")
        _color = color.substring(1);
    if (_color.length != 6)
        return '';

    _color = color.toLowerCase()

    var rgb = new Array();
    for (var x = 0; x < 3; x++) {
        rgb[0] = _color.substr(x * 2, 2)
        rgb[3] = "0123456789abcdef";
        rgb[1] = rgb[0].substr(0, 1)
        rgb[2] = rgb[0].substr(1, 1)
        rgb[20 + x] = rgb[3].indexOf(rgb[1]) * 16 + rgb[3].indexOf(rgb[2])
    }
    return 'rgba(' + rgb[20] + ',' + rgb[21] + ',' + rgb[22] + ',' + opacity + ')';
}
```
