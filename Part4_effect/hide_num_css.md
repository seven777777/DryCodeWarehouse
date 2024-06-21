# 纯 CSS 实现标签自动显示超出数量

<div class="hide-num-wrap" >
    <ul class="hide-num-con">
        <li class="tag">HTML</li>
        <li class="tag">CSS</li>
        <li class="tag">JavaScript</li>
        <li class="tag">Flutter</li>
        <li class="tag">Vue</li>
        <li class="tag">React</li>
        <li class="tag">Svelte</li>
    </ul>
</div>
<style>
.markdown-section ol, .markdown-section ul{
    list-style:none;
    margin-bottom:0;
}
.hide-num-wrap {
    width: 300px;
    display: flex;
    align-items: center;
    padding: 15px;
    outline: 2px solid #9747ff;
    gap: 5px;
    overflow: hidden;
    margin-top: 20px;
    &::after {
        content: '+' counter(num);
        padding: 0.2em 0.5em;
        background-color: #ffe8a3;
        color: #191919;
        border-radius: 4px;
    }
}
.hide-num-con {
    position: relative;
    display: flex;
    gap: 5px;
    padding: 5px;
    overflow: hidden;
    counter-reset: num;
    animation: check;
    animation-timeline: scroll(x self);
    margin-right: -46px;
    .tag {
        padding: 0.2em 0.5em;
        background-color: #9747ff;
        color: #fff;
        border-radius: 4px;
        counter-increment: num 1;
        animation: appear;
        animation-timeline: view(inline);
        animation-range: contain;
    }
}
@keyframes check {
    from,
    to {
        margin-right: 0;
        -webkit-mask: linear-gradient(to right, #fff calc(100% - 30px), transparent);
    }
}
@keyframes appear {
    from,
    to {
        counter-increment: num 0;
        background-color: #4d47ff;
    }
}
</style>

```html
<div class="hide-num-wrap">
    <ul class="hide-num-con">
        <li class="tag">HTML</li>
        <li class="tag">CSS</li>
        <li class="tag">JavaScript</li>
        <li class="tag">Flutter</li>
        <li class="tag">Vue</li>
        <li class="tag">React</li>
        <li class="tag">Svelte</li>
    </ul>
</div>
```

```css
* {
    list-style: none;
}
.hide-num-wrap {
    width: 300px;
    display: flex;
    align-items: center;
    padding: 15px;
    outline: 2px solid #9747ff;
    gap: 5px;
    overflow: hidden;
    margin-top: 20px;
    &::after {
        content: '+' counter(num);
        padding: 0.2em 0.5em;
        background-color: #ffe8a3;
        color: #191919;
        border-radius: 4px;
    }
}
.hide-num-con {
    position: relative;
    display: flex;
    gap: 5px;
    padding: 5px;
    overflow: hidden;
    counter-reset: num;
    animation: check;
    animation-timeline: scroll(x self);
    margin-right: -46px;
    .tag {
        padding: 0.2em 0.5em;
        background-color: #9747ff;
        color: #fff;
        border-radius: 4px;
        counter-increment: num 1;
        animation: appear;
        animation-timeline: view(inline);
        animation-range: contain;
    }
}
@keyframes check {
    from,
    to {
        margin-right: 0;
        -webkit-mask: linear-gradient(to right, #fff calc(100% - 30px), transparent);
    }
}
@keyframes appear {
    from,
    to {
        counter-increment: num 0;
        background-color: #4d47ff;
    }
}
```
