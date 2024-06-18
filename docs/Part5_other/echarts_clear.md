# echarts 图变模糊解决办法

## 方法一:使用 svg 渲染方式渲染 echarts 图

```
echarts.init(this.$refs.line, null, { renderer: "svg" })
```

## 方法二:通过 devicePixelRatio 调整清晰度

```
echarts.init(this.$refs.line,null, {devicePixelRatio: 2.5})
```
