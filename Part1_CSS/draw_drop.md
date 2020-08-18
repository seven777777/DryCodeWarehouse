# 绘制水滴形状样式

```css
span {
  height: 40px;
  width: 40px;
  display: block;
  position: relative;
}
.nav {
  width: 26px;
}
.nav:before {
  content: '';
  height: 26px;
  width: 26px;
  display: block;
  position: absolute;
  top: 38px;
  left: 15px;
  z-index: 1;
  line-height: 26px;
  background: #6ccddf;
  border-radius: 40px;
  -webkit-border-radius: 40px;
  -moz-border-radius: 40px;
  color: #fff;
  text-align: center;
}
.nav:after {
  content: '';
  height: 0px;
  width: 0px;
  border: 10px transparent solid;
  display: block;
  position: absolute;
  bottom: -2px;
  left: 18px;
  border-right: 10px solid transparent;
  border-bottom: 15px solid #6ccddf;
  border-left: 10px solid transparent;
}
```

