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
    piece:number , // 选填、宽度切开段数
    segment:number, //选填、高度切开的段数[截数]
}
```

#### 生成后可以获取以下数据

1. scrollData --> 绘制画布小块的数据（instanceof === ImageData）
2. scrollUrl --> 绘制画布小块的base64数据
3. finishData --> 绘制画布的已经打乱的数据（instanceof === ImageData）
4. finishUrl --> 绘制画布的已经打乱的base64数据
5. coefficient --> 用于还原已打乱数据的唯一值（估计有6W多种可能）
6. verifyValue: number --> 正确的校验值

### 2、还原图像

```javascript
JSONParam = {
    ctx: "", //必填，绘制还原后的图像的画布容器
    scrollCtx: "", //必填，绘制拼图滑块的容器
    finishData:"", //必填，需要还原的数据
    scrollData:"", //必填，拼图滑块的数据
    coefficient:"", //必填，用于还原图像的唯一值
    piece:number , // 选填、宽度切开段数（如果生成的时候输入了则此处必须一样）
    segment:number, //选填、高度切开的段数[截数]（如果生成的时候输入了则此处必须一样）
   // 还原的时候还可以选填 也可以自行控制
    handlerScrollDom: '', // 控制滑动拼图的容器
    scrrollContainer: '', // 鼠标允许的操作范围的容器
    offsetScroll: number, // 控制滑动拼图的容器的偏移值
    moveStop: Function, // 移动结束的回调函数
}
```

