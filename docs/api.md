# 一个入口简单入手

## initScrollCheck(JOSNParam)

### 1、输入生成打乱的图像和数据

```javascript
JOSNParam = {
    input:"输入的源", //必填
    createConfig: {}, //必填、Object / boolean
    width:"" ,//选填、画布的宽度（不传默认为ctx的大小或者320）
    height:"",//选填、画布的宽度（不传默认为ctx的大小或者320）
    ctx:"" ,//选填、绘制打乱后的画布
    scrollCtx:"", //选填、绘制拼图小块的画布
    autoMakeDate:false,//选填、是否自动生成数据
}
```

#### 生成后可以获取以下数据

1. scrollData --> 绘制画布小块的数据（instanceof === ImageData）
2. scrollUrl --> 绘制画布小块的base64数据
3. finishData --> 绘制画布的已经打乱的数据（instanceof === ImageData）
4. finishUrl --> 绘制画布的已经打乱的base64数据
5. coefficient --> 用于还原已打乱数据的唯一值（估计有6W多种可能）
6. verifyValue: number --> 正确的校验值

### 2、

