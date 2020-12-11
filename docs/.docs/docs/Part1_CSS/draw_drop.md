# 绘制水滴形状样式

```scss
.dropmarker{
    width: 26px;
    height: 26px;
    position: relative;
    border-radius: 50%;
    background: #6ccddf;
    line-height: 26px;
    text-align: center;
    color: white;
    &:after {
        content: '';
        width: 0px;
        height: 0px;
        border: 10px transparent solid;
        position: absolute;
        bottom: -20px;
        left: 50%;
        transform: translateX(-50%);
        border-right: 10px solid transparent;
        border-top: 15px solid #6ccddf;
        border-left: 10px solid transparent;
    }
}
```

