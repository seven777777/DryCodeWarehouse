# 滚动条样式美化

```css
 /* 滚动条样式 */
div::-webkit-scrollbar {
    width: 8px;
    height: 1px;
}
div::-webkit-scrollbar-thumb {
    border-radius: 4px;
    box-shadow: inset 0 0 5px rgba(182, 176, 176, 0.2);
    background: #EEF4FA;//滚动条颜色
}
div::-webkit-scrollbar-track {
    box-shadow: none;
    border-radius: 4px;
    background: transparent;//底色
}
```

