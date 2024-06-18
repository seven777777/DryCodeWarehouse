# 优惠券-内圆角带阴影

<img src="../images/part4/coupon/pic01.png" alt="" />

```css
/* css */
.coupon-box {
    width: 250px;
    height: 80px;
    filter: drop-shadow(2px 1px 5px rgba(0, 0, 0, 0.5));
    display: flex;
}

.coupon-box-left,
.coupon-box-right {
    position: relative;
}

.coupon-box-left {
    flex: 1;
    background: radial-gradient(circle at top right, transparent 8px, #FA725B 0) top right,
        radial-gradient(circle at bottom right, transparent 8px, #FA725B 0) bottom right;
    background-size: 100% 50%;
    background-repeat: no-repeat;
    border-radius: 4px 0 0 4px;

}

.coupon-box-left::after {
    content: '';
    width: 1px;
    position: absolute;
    top: 8px;
    right: 0;
    bottom: 8px;
    background: linear-gradient(#e9e9e9 50%, transparent 0);
    background-size: 100% 5px;
}

.coupon-box-right {
    width: 80px;
    background: radial-gradient(circle at top left, transparent 8px, #fff 0) top left,
        radial-gradient(circle at bottom left, transparent 8px, #fff 0) bottom left;
    background-size: 100% 50%;
    background-repeat: no-repeat;
    border-radius: 0 4px 4px 0;
}
```

```html
<!-- html -->
<div class="coupon-box">
    <div class="coupon-box-left"></div>
    <div class="coupon-box-right"></div>
</div>
```