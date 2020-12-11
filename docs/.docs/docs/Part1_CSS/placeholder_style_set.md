# placeholder样式设置

```css
input::-webkit-input-placeholder{   /* WebKit, Blink, Edge */
    color:red;
}
input::-moz-placeholder{   /* Mozilla Firefox 19+ */
    color:red;
}
input:-moz-placeholder{    /* Mozilla Firefox 4 to 18 */
    color:red;
}
input:-ms-input-placeholder{  /* Internet Explorer 10-11 */ 
    color:red;
}
```

#### 扩展

```scss
// scss—— mixin 封装
@mixin placeholder-color($color) {
    &::-webkit-input-placeholder {
        /* WebKit, Blink, Edge */
        color: $color;
    }
    &:-moz-placeholder {
        /* Mozilla Firefox 4 to 18 */
        color: $color;
    }
    &::-moz-placeholder {
        /* Mozilla Firefox 19+ */
        color: $color;
    }
    &:-ms-input-placeholder {
        /* Internet Explorer 10-11 */
        color: $color;
    }
}

// 使用
input{
    @include placeholder-color(#AEAEAE)
}
```

