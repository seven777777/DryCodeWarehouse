# canvas圆环组件

<img src="../images/part4/canvas_circle/pic01.png" alt="" />

```html
<canvas id="canvas" width="300" height="200"></canvas>
```

```js
let width = 300, height = 200;//canvas画纸宽高
let radius = '90%';// 控制大小 ********
// 基础圆环色值
let baseColor = '#F3F6FD'
// 描边色值（可以单色字符串，可以数组色值渐变）
let coverColor = ['#FDEE9A', '#F76B1C']
// 不带单位的百分值，90%—90
let value = 90 //控制填充百分比 ********
let percent = (value + '').split('%')[0]
if (!isNaN(percent)) {
    percent = Number(percent)
} else {
    percent = 0
}
// 外层半径
let baseLength = width > height ? height : width
let basePercent = radius.split('%')[0] / 100
let outR = (baseLength * basePercent) / 2
// 内层半径
let innerR = outR - 6

setTimeout(() => {
    baseDraw(percent)
})

/**
 * 顺时针方向画图，起始点在左侧
 * @param  {[number]} percent
 */
function baseDraw(percent) {
    if (percent > 100 || percent < 0) return
    var c = $("#canvas")[0],
        ctx = c.getContext('2d'),
        cWidth = c.width,
        cHeight = c.height,
        PI = Math.PI,
        sA = (Math.PI * 5) / 6
    var baseRadius = PI + (PI - sA) * 2 //始终保证与初始角度对称，计算基于顺时针画图
    var step = baseRadius / 100 // 一个1%对应的弧度大小
    var sE = sA + baseRadius

    var baseEnd = sA + step * percent

    var baseStrokeStyle
    if (!Array.isArray(coverColor)) {
        baseStrokeStyle = coverColor
    } else {
        if (coverColor.length == 2) {
            const arrList = gradient(coverColor[0], coverColor[1], 100)
            // 创建一个渐变，参数为：开始x坐标、开始y坐标、结束x坐标、结束y坐标、
            var grd = ctx.createLinearGradient(0, 0, (PI * innerR * 2 * 3) / 4, 0)
            // 为渐变添加颜色，参数1表示渐变开始和结束之间的位置（用0至1的占比表示），参数2位颜色
            grd.addColorStop(0, arrList[0])
            // grd.addColorStop(0.8, arrList[parseInt(percent)])
            grd.addColorStop(1, arrList[parseInt(percent) > 0 ? parseInt(percent) - 1 : 0])
            baseStrokeStyle = grd
        }
    }

    // 画灰色圆弧
    drawCanvas(ctx, cWidth / 2, (cHeight * 3) / 4, outR, sA, sE, baseColor, 2) //外实线圆弧
    drawCanvas(ctx, cWidth / 2, (cHeight * 3) / 4, innerR, sA, sE, baseColor, 1, 'dashed') //内虚线圆弧

    if (percent != 0) {
        // 画主体部分圆弧
        drawCanvas(ctx, cWidth / 2, (cHeight * 3) / 4, outR, sA, baseEnd, baseStrokeStyle, 2) //外实线圆弧
        drawCanvas(ctx, cWidth / 2, (cHeight * 3) / 4, innerR, sA, baseEnd, baseStrokeStyle, 1, 'dashed') //内虚线圆弧
        // 画圆终点
        var angle = 2 * PI - baseEnd // 转换成逆时针方向的弧度（三角函数中的）
        var xPos = Math.cos(angle) * outR + cWidth / 2 // 终点圆 圆心的x坐标
        var yPos = -Math.sin(angle) * outR + (cHeight * 3) / 4 // 终点圆 圆心的y坐标
        drawCanvas(ctx, xPos, yPos, 1, 0, 2 * PI, baseEnd, 1)
    }
}
/**
 * x,y：圆心坐标
 * r：圆半径
 * sAngle,eAngle：起止角度（弧度记）
 */
function drawCanvas(ctx, x, y, r, sAngle, eAngle, color, lineWidth, lineStyle = 'solid') {
    ctx.beginPath()
    ctx.lineCap = 'round'
    ctx.strokeStyle = color
    ctx.lineWidth = lineWidth
    ctx.setLineDash(lineStyle == 'dashed' ? [3] : [])
    ctx.arc(x, y, r, sAngle, eAngle, false)
    ctx.stroke()
}
/**
 * 计算渐变过渡色
 * @param {*} startColor
 * @param {*} endColor
 * @param {*} step
 */
function gradient(startColor, endColor, step) {
    // 将 hex 转换为rgb
    var sColor = hexToRgb(startColor),
        eColor = hexToRgb(endColor)

    // 计算R\G\B每一步的差值
    var rStep = (eColor[0] - sColor[0]) / step,
        gStep = (eColor[1] - sColor[1]) / step,
        bStep = (eColor[2] - sColor[2]) / step

    var gradientColorArr = []
    for (var i = 0; i < step; i++) {
        // 计算每一步的hex值
        gradientColorArr.push(rgbToHex(parseInt(rStep * i + sColor[0]), parseInt(gStep * i + sColor[1]), parseInt(bStep * i + sColor[2])))
    }
    return gradientColorArr
}
//计算两个颜色之间的渐变色值
function rgbToHex(r, g, b) {
    var hex = ((r << 16) | (g << 8) | b).toString(16)
    return '#' + new Array(Math.abs(hex.length - 7)).join('0') + hex
}
function hexToRgb(hex) {
    var rgb = []
    for (var i = 1; i < 7; i += 2) {
        rgb.push(parseInt('0x' + hex.slice(i, i + 2)))
    }
    return rgb
}
```