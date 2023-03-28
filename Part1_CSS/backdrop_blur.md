# 高斯模糊蒙版

<div class="box">这里是一些内容</div>
<style>
    .box{
        width:100px;
        height:100px;
        position:relative;
    }
    .box::before{
        content:"";
        position:absolute;
        top:0;
        right:0;
        bottom:0;
        left:0;
        background-color:rgba(0,0,0,0.1);
        backdrop-filter:blur(3px);
    }
</style>

> 蒙层下必须要有内容

```
<!-- 关键属性 -->
backdrop-filter:blur(3px);//值越大，模糊效果越明显
```
