# 纯 CSS 实现文本超过行数展开收起

<div class="text-wrap">
    <p class="hide-txt">
        <label class="hide-txt-expand">
            <input type="checkbox" hidden />
        </label>
        这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互
    </p>
</div>
<style>
p{
    margin:0;
}
.text-wrap {
    display: flex;
    position: relative;
    width: 300px;
    padding: 8px;
    outline: 1px dashed #9747ff;
    border-radius: 4px;
    line-height: 1.5;
    text-align: justify;
    font-family: cursive;
    margin-top: 20px;
}
.hide-txt {
    animation: checkHide 1s;
    animation-timeline: scroll(self);
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 3;
    --trunc: false;
}
.hide-txt::before {
    content: '';
    float: right;
    height: calc(100% - 24px);
}
.hide-txt-expand {
    font-size: 80%;
    padding: 0.2em 0.5em;
    background-color: #9747ff;
    color: #fff;
    border-radius: 4px;
    cursor: pointer;
    float: right;
    clear: both;
}
.hide-txt-expand::after {
    content: '展开';
}

.text-wrap:has(:checked) .hide-txt {
-webkit-line-clamp: 999;
}
.text-wrap:has(:checked) .hide-txt-expand {
display: initial;
}
.text-wrap:has(:checked) .hide-txt-expand::after {
content: '收起';
}

@keyframes checkHide {
from,
to {
--trunc: true;
}
}
@container style (--trunc:true) {
.hide-txt-expand {
display: initial;
}
}
</style>

```html
<div class="text-wrap">
    <p class="hide-txt">
        <label class="hide-txt-expand">
            <input type="checkbox" hidden />
        </label>
        这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互这是一段测试文字，用来试验纯css检测文本是否溢出，并据此增加交互
    </p>
</div>
```

```css
.text-wrap {
    display: flex;
    position: relative;
    width: 300px;
    padding: 8px;
    outline: 1px dashed #9747ff;
    border-radius: 4px;
    line-height: 1.5;
    text-align: justify;
    font-family: cursive;
    margin-top: 20px;
}
.hide-txt {
    animation: checkHide 1s;
    animation-timeline: scroll(self);
    overflow: hidden;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 3;
    --trunc: false;
}
.hide-txt::before {
    content: '';
    float: right;
    height: calc(100% - 24px);
}
.hide-txt-expand {
    font-size: 80%;
    padding: 0.2em 0.5em;
    background-color: #9747ff;
    color: #fff;
    border-radius: 4px;
    cursor: pointer;
    float: right;
    clear: both;
}
.hide-txt-expand::after {
    content: '展开';
}

.text-wrap:has(:checked) .hide-txt {
    -webkit-line-clamp: 999;
}
.text-wrap:has(:checked) .hide-txt-expand {
    display: initial;
}
.text-wrap:has(:checked) .hide-txt-expand::after {
    content: '收起';
}

@keyframes checkHide {
    from,
    to {
        --trunc: true;
    }
}
@container style (--trunc:true) {
    .hide-txt-expand {
        display: initial;
    }
}
```
