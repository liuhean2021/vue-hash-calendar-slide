![demo1.gif](https://file.allsmy.com/vhcs/demo1.gif)
![demo2.gif](https://file.allsmy.com/vhcs/demo2.gif)
<br/>
原图1：https://file.allsmy.com/vhcs/demo1.mov
原图2：https://file.allsmy.com/vhcs/demo2.mov
<br/>上图只是配置中部分功能,更多演示参照下面运行项目

# vue-hash-calendar-slide
- 基于 vue 2.X 开发的日历组件
- 原生 js 开发，没引入第三方库
- 上下滑动切换周/月模式，左右滑动切换月份
- 支持外部传参控制上下滑动，方便复杂页面集成
- 日期标记支持5种类型：日期颜色、日期背景色、日期底部原点、日期右上角标记、日期底部文字
- 更多更新查看提交日志：
  https://github.com/liuhean2021/vue-hash-calendar-slide/commits/master

### 1. 体验效果请先克隆仓库 地址: https://github.com/liuhean2021/vue-hash-calendar-slide
### 2. 本地运行仓库，安装依赖命令： npm i 启动项目命令： npn run server
### 3. 运行成功后浏览器访问： http://localhost:8080/


# 安装使用说明

```
npm i vue-hash-calendar-slide
```

```
// 在入口文件中（main.js）或vue组件里，导入组件库
import vueHashCalendarSlide from 'vue-hash-calendar-slide'
// 引入组件CSS样式
import 'vue-hash-calendar-slide/lib/vue-hash-calendar-slide.css'
// 注册组件库
Vue.use(vueHashCalendarSlide)
```

```
// 在VUE文件中引入组件
 <vue-hash-calendar-slide/>
```

# API

| 属性                      | 说明                                                                                                                                                                                                                                                                                                                                                            |    类型    |            默认            | 是否必传 |
|:------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------:|:------------------------:| :------: |
| disabledDate            | 设置日期的禁用状态，参数为当前日期，要求返回 Boolean （禁用该日期需返回 true）                                                                                                                                                                                                                                                                                                                | Function |           ---            |    否    |
| markDate                | 需要被标记的日期，如：[{ color: 'rgba(187,27,27,0.3)', type: 'background', date: ['2021/12/20'] },{ color: '#76f105', type: 'dateColor', date: [ '2021/12/21'] },{ color: '#ff0000', type: 'dot', date: ['2021/12/22'] },{ color: '#133fcf', type: 'topRightIcon', date: [ '2021/12/23'] },{ color: '#b7bc1f', text: '节假日', type: 'bottomText', date: ['2021/12/24'] } ] |  Array   |            []            |    否    |
| showArrowIcon           | 显示底部的箭头按钮切换周/月模式；启用默认禁用上下滑动切换周/月                                                                                                                                                                                                                                                                                                                              | Boolean  |          false           | 否 |
| borderBoxShadow         | 控件边框的阴影控制，如：'0 5px 10px 0px rgba(203,203,203,0.5)'                                                                                                                                                                                                                                                                                                            |  String  |            ''            | 否 |
| contentColor            | 控件整体日期颜色控制                                                                                                                                                                                                                                                                                                                                                    |  String  |        '#FFFFFF'         | 否 |
| disableColor            | 非当前月份或禁用日期的颜色                                                                                                                                                                                                                                                                                                                                                 |  String  |        '#c0c4cc'         | 否 |
| swipeStatus             | 滑动状态参数从外部传入控制，用于复杂页面对滑动动作的控制，支持up,down,left,right                                                                                                                                                                                                                                                                                                             |  String  |            ''            | 否 |
| mainBackgroundColor     | 控件的整体背景色控制                                                                                                                                                                                                                                                                                                                                                    |  String  |        '#0e8ee9'         | 否 |
| visible                 | 控制日历组件的显示或隐藏,需使用 `.sync` 修饰符                                                                                                                                                                                                                                                                                                                                  | Boolean  |          false           |    否    |
| scrollChangeDate        | 控制滑动的时候是否修改选中的日期                                                                                                                                                                                                                                                                                                                                              | Boolean  |           true           |    否    |
| model                   | 日历组件以哪种形式展示。inline：内联的方式。dialog：弹窗的方式                                                                                                                                                                                                                                                                                                                         |  String  |          inline          |    否    |
| defaultDatetime         | 指定默认时间。                                                                                                                                                                                                                                                                                                                                                       |   Date   |           当前时间           |    否    |
| format                  | 确认日期时，回调事件返回的日期格式。如“YY/MM/DD hh:mm” 、“YY 年 MM 月第 DD 天，当前时间 hh 时 mm 分”、“MM DD,YY at hh:mm F”                                                                                                                                                                                                                                                                   |  String  |      YY/MM/DD hh:mm      |    否    |
| weekStart               | 以星期几作为日历每一周的起始星期。可选['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday']                                                                                                                                                                                                                                                             |  String  |          sunday          |    否    |
| pickerType              | 选择器类型 datetime：日期+时间 date：日期 time：时间                                                                                                                                                                                                                                                                                                                          |  String  |         datetime         |    否    |
| showTodayButton         | 是否显示返回今日按钮                                                                                                                                                                                                                                                                                                                                                    | Boolean  |           true           |    否    |
| isShowWeekView          | 是否以周视图展示组件                                                                                                                                                                                                                                                                                                                                                    | Boolean  |          false           |    否    |
| disabledWeekView        | 禁用周视图（设置为 true 后，无法上下滑动进行周/月切换）                                                                                                                                                                                                                                                                                                                               | Boolean  |          false           |    否    |
| minuteStep              | 间隔时间。（分钟的步长）                                                                                                                                                                                                                                                                                                                                                  |  Number  |            1             |    否    |
| lang                    | 选择的语言版本。可选值:['CN', 'EN']                                                                                                                                                                                                                                                                                                                                      |  String  |            CN            |    否    |


- 如果有其他问题， 或者功能上不兼容的。可以github提交 issue。
