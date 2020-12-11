# 色值转换Hex转rgb
```js
hexToRgb(hex){
    var rgb = [];
    for(var i=1; i<7; i+=2){
        rgb.push(parseInt("0x" + hex.slice(i,i+2)));
    }
    return rgb;
}
```
