# echarts图变模糊解决办法

## 方法一:使用svg渲染方式渲染echarts图
```
echarts.init(this.$refs.line, null, { renderer: "svg" })
```
## 方法二:通过devicePixelRatio调整清晰度
```
echarts.init(this.$refs.line,null, {devicePixelRatio: 2.5})
```



