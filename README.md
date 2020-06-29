# vue-schedule-calendar

[demo](https://yscoder.github.io/vue-schedule-calendar/)

## Install

```bash
安装插件
npm i vue-schedule-calendar -S

引入插件
import schedulecalendar from 'vue-schedule-calendar'
 components:{
      schedulecalendar
    }
页面导入 
    <schedulecalendar :events="events"
                            :dateItemRender="itemRender"
                            @event-dragend="changeDate"></schedulecalendar>
    
```


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
