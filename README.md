![calendar.gif](https://www.allsmy.com/resource/vue-hash-calendar-slide.gif)
<br/>上图只是配置中部分功能,更多演示参照下面运行项目

# vue-hash-calendar-slide

# 1. 体验效果请先克隆仓库 地址: https://github.com/liuhean2021/vue-hash-calendar-slide
# 2. 本地运行仓库，安装依赖命令： npm i 启动项目命令： npn run server
# 3. 运行成功后浏览器访问： http://localhost:8080/
# 4. 有很多配置属性懒得写出来，可自行修改参数查看效果
# 5. 如果需要其他功能，可以自己修改代码，或者提问题

- 更多更新查看提交日志：
  https://github.com/liuhean2021/vue-hash-calendar-slide/commits/master
- 增加禁用日期颜色控制
- 增加外部传参控制上下滑动，方便复杂页面集成
- 修复左右滑动过程中触发点击事件的bug
- 增加更换背景色
- 增加日期背景色标记
- 基于 vue 2.X 开发的日历组件
- 支持手势滑动操作
- 原生 js 开发，没引入第三方库
- 上下滑动 切换 周/月 模式

# 安装使用说明

```
npm i vue-hash-calendar-slide
```

```
// 在入口文件中（main.js），导入组件库
import vueHashCalendarSlide from 'vue-hash-calendar-slide'
// 引入组件CSS样式
import 'vue-hash-calendar-slide/lib/vue-hash-calendar-slide.css'
// 注册组件库
Vue.use(vueHashCalendarSlide)
```

```
// 在VUE文件中引入组件
 <vue-hash-calendar-slide></vue-hash-calendar-slide>
```

## github 地址：[https://github.com/liuhean2021/vue-hash-calendar-slide](https://github.com/liuhean2021/vue-hash-calendar-slide)

# API

| 属性             | 说明                                                                                                                                                  |   类型   |      默认      | 是否必传 |
| :--------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------- | :------: | :------------: | :------: |
| disableColor     | 非当前月份或禁用日期的颜色         | String | '#c0c4cc' | 否 |
| swipeStatus      | 外部传入的滑动控制，支持up,down,left,right        | String | '' | 否 |
| mainBackgroundColor      | 背景色        | String | '#0e8ee9' | 否 |
| visible          | 控制日历组件的显示或隐藏,需使用 `.sync` 修饰符                                                                                                        | Boolean  |     false      |    否    |
| scrollChangeDate | 控制滑动的时候是否修改选中的日期                                                                                                                      | Boolean  |      true      |    否    |
| model            | 日历组件以哪种形式展示。inline：内联的方式。dialog：弹窗的方式                                                                                        |  String  |     inline     |    否    |
| defaultDatetime  | 指定默认时间。                                                                                                                                        |   Date   |    当前时间    |    否    |
| format           | 确认日期时，回调事件返回的日期格式。如“YY/MM/DD hh:mm” 、“YY 年 MM 月第 DD 天，当前时间 hh 时 mm 分”、“MM DD,YY at hh:mm F”                           |  String  | YY/MM/DD hh:mm |    否    |
| weekStart        | 以星期几作为日历每一周的起始星期。可选['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday']                                  |  String  |     sunday     |    否    |
| pickerType       | 选择器类型 datetime：日期+时间 date：日期 time：时间                                                                                                  |  String  |    datetime    |    否    |
| showTodayButton  | 是否显示返回今日按钮                                                                                                                                  | Boolean  |      true      |    否    |
| isShowWeekView   | 是否以周视图展示组件                                                                                                                                  | Boolean  |     false      |    否    |
| disabledWeekView | 禁用周视图（设置为 true 后，无法上下滑动进行周/月切换）                                                                                               | Boolean  |     false      |    否    |
| disabledDate     | 设置日期的禁用状态，参数为当前日期，要求返回 Boolean （禁用该日期需返回 true）                                                                        | Function |      ---       |    否    |
| markDate         | 需要被标记的日期，可按不同颜色分组标记（不分组默认蓝色）。如：[{color: 'red',type: 'background', date: ['2019/02/25']},{color: 'blue', type: 'dot', date: ['2019/01/20']},'2019/03/20'] |  Array   |       []       |    否    |
| minuteStep       | 间隔时间。（分钟的步长）                                                                                                                              |  Number  |       1        |    否    |
| lang             | 选择的语言版本。可选值:['CN', 'EN']                                                                                                                   |  String  |       CN       |    否    |


- 如果有其他问题， 或者功能上不兼容的。可以邮件沟通 allsmy.com@gmail.com，或者 github 提交 issue。
