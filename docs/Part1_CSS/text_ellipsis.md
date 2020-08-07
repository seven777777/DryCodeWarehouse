# 文本省略

### 单行省略

```css
{
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
```

### 多行省略

```css
{
    display: -webkit-box;
    -webkit-line-clamp: $line;//$line:行数
    -webkit-box-orient: vertical;
    overflow: hidden;
}
```

