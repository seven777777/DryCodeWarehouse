# 边框发光转动动画

## 效果

<div class="demo-box">
    <div class="outer">
        <div class="moving-element"></div>
        <div class="inner"></div>
    </div>
</div>

<style>
.demo-box {
    width: 100%;
    height: 400px;
    background: rgb(9, 9, 11);
    overflow: hidden;
    box-sizing: border-box;
}
.outer {
    width: 400px;
    height: 200px;
    margin: 100px;
    padding: 1px;
    position: relative;
    border-radius: 20px;
    overflow: hidden;
}
.inner {
    background: rgba(9, 9, 11, 0.38);
    position: absolute;
    left: 1px;
    top: 1px;
    right: 1px;
    bottom: 1px;
    border-radius: 20px;
    border: 1px solid rgb(30, 41, 59);
    backdrop-filter: blur(24px);
}
.moving-element {
    position: absolute;
    top: 0;
    left: 0;
    width: 80px;
    height: 80px;
    animation: moveAround 8s linear infinite;
    border-radius: 40px;
    transform: translate(-40px, -40px);
    background-image: radial-gradient(#cbacf9 40%, transparent 80%);
}
@keyframes moveAround {
    0% {
        left: 40px;
        top: 0px;
    }
    28.93% {
        left: 360px;
        top: 0px;
    }
    33.99% {
        left: 400px;
        top: 40px;
    }
    44.82% {
        left: 400px;
        top: 160px;
    }
    49.88% {
        left: 360px;
        top: 200px;
    }
    78.81% {
        left: 40px;
        top: 200px;
    }
    83.87% {
        left: 0px;
        top: 160px;
    }
    94.70% {
        left: 0px;
        top: 40px;
    }
    100% {
        left: 40px;
        top: 0px;
    }
}

</style>

## 代码

```html
<div class="demo-box">
    <div class="outer">
        <div class="moving-element"></div>
        <div class="inner"></div>
    </div>
</div>
```

```css
.demo-box {
    width: 100%;
    height: 400px;
    background: rgb(9, 9, 11);
    overflow: hidden;
    box-sizing: border-box;
}
.outer {
    width: 400px;
    height: 200px;
    margin: 100px;
    padding: 1px;
    position: relative;
    border-radius: 20px;
    overflow: hidden;
}
.inner {
    background: rgba(9, 9, 11, 0.38);
    position: absolute;
    left: 1px;
    top: 1px;
    right: 1px;
    bottom: 1px;
    border-radius: 20px;
    border: 1px solid rgb(30, 41, 59);
    backdrop-filter: blur(24px);
}
.moving-element {
    position: absolute;
    top: 0;
    left: 0;
    width: 80px;
    height: 80px;
    animation: moveAround 8s linear infinite;
    border-radius: 40px;
    transform: translate(-40px, -40px);
    background-image: radial-gradient(#cbacf9 40%, transparent 80%);
}
@keyframes moveAround {
    0% {
        left: 40px;
        top: 0px;
    }
    28.93% {
        left: 360px;
        top: 0px;
    }
    33.99% {
        left: 400px;
        top: 40px;
    }
    44.82% {
        left: 400px;
        top: 160px;
    }
    49.88% {
        left: 360px;
        top: 200px;
    }
    78.81% {
        left: 40px;
        top: 200px;
    }
    83.87% {
        left: 0px;
        top: 160px;
    }
    94.70% {
        left: 0px;
        top: 40px;
    }
    100% {
        left: 40px;
        top: 0px;
    }
}
```
