# 常用时间计算
Moment
```
moment().add(-30, 'd').format("YYYY年MM月DD日");//前30天
moment().add(-1, '').format("YYYY年MM月DD日");//前1年
moment(endTime).diff(moment(startTime), 'years')//两个日期/时间的时差
```
