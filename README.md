# vue-schedule
## 在原作者的插件vue-schedule-calendar上做了一些修改

[demo](https://liqz2009.github.io/vue-schedule/)


## Install

```bash
安装插件
npm install vue-schedule https://github.com/liqz2009/vue-schedule.git

引入插件
import schedulecalendar from 'vue-schedule'
 components:{
      schedulecalendar
    }
页面导入
    <schedulecalendar :events="events"
                @event-dragend="changeDate"></schedulecalendar>

```


## 事件

1. date-click(e,date)       点击日期
2. event-click(e,item)       点击标签
3. event-dragend(e,item,date)  拖曳结束
4. event-dragstart(e,item,date)  拖曳开始
5. event-dragenter(e,item,date)  拖曳中
6. month-change(year,month)   月份改变



## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

## Todo List

*   [x] 年、月选择器
*   [ ] 跨天显示
*   [x] 自定义数据展示模版
*   [ ] 起止时间限制
*   [x] 常用事件支持
*   [ ] 过期标记
*   [ ] 快捷键
*   [ ] i18n
