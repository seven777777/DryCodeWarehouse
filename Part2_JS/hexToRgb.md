# 色值转换Hex转rgb
```js
hexToRgb(hex){
    var rgb = [];
    for(var i=0; i<6; i+=2){
        rgb.push(parseInt("0x" + hex.slice(i,i+2)));
        // rgb.push(parseInt(hex.slice(i,i+2),16))
    }
    return rgb;
}
```
