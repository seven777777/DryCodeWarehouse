# 计算两个色值中的过渡色值
```js
hexToRgb(hex){
    var rgb = [];
    for(var i=0; i<6; i+=2){
        rgb.push(parseInt("0x" + hex.slice(i,i+2)));
        // rgb.push(parseInt(hex.slice(i,i+2),16))
    }
    return rgb;
}

rgbToHex(r, g, b){
    var hex = ((r<<16) | (g<<8) | b).toString(16);
    return "#" + new Array(Math.abs(hex.length-7)).join("0") + hex;
}

/**
 * 计算渐变过渡色
 * @param {*} startColor 
 * @param {*} endColor 
 * @param {*} step 
 */
gradient (startColor,endColor,step){
    // 将 hex 转换为rgb
    var sColor = this.hexToRgb(startColor),
        eColor = this.hexToRgb(endColor);

    // 计算R\G\B每一步的差值
    var rStep = (eColor[0] - sColor[0]) / step,
        gStep = (eColor[1] - sColor[1]) / step,
        bStep = (eColor[2] - sColor[2]) / step;

    var gradientColorArr = [];
    for(var i=0;i<step;i++){
        // 计算每一步的hex值
        gradientColorArr.push(this.rgbToHex(parseInt(rStep*i+sColor[0]),parseInt(gStep*i+sColor[1]),parseInt(bStep*i+sColor[2])));
    }
    return gradientColorArr;
}
```

实际应用参考这篇博客：[https://seven777777.github.io/myblog/work/2020/12/11/color-gradient/](https://seven777777.github.io/myblog/work/2020/12/11/color-gradient/)
