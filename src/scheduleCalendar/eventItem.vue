<template>
    <div class="schedule-calendar-details" style="top: 0px; left: 0px;" @click="onClick" @dragstart="onDrag" >
        <a class="schedule-calendar-details-hd" >

        </a>
        <div data-v-1a6af121="" class="schedule-calendar-details-bd">
            <div draggable="true" :class="statusClass(item.status)">
                <span> [{{getTime(item.date)}}]{{item.text}}</span>
            </div>
        </div>
    </div>
</template>
<script>
    import {
        EventBus
    } from './utils'

    export default {
        props: {
            item: Object,
            date: Date,
            type: String,
            itemRender: Function
        },
        methods: {
            onDrag(e) {
                this.$emit('item-dragstart', e, this.item, this.date, this.type)
            },
            onClick(e) {
                e.stopPropagation()
                e.preventDefault()
                EventBus.$emit('item-click', e, this.item)
            },
            statusClass(status)
            {
                return "schedule-calendar-detail-item schedule-calendar-status_"+status;
            },
            getTime(date)
            {
                let d= new Date(date);
                let timeString=d.getHours();
                if(d.getHours()<10)
                {
                    timeString='0'+d.getHours();
                }
                if(d.getMinutes()<10)
                {
                    timeString+=':0'+d.getMinutes();
                }
                else{
                    timeString+=':'+d.getMinutes();
                }
                return timeString;
            }
        },
        // render(h) {
        //     return h('div', {
        //         class: ['schedule-calendar-detail-item', `schedule-calendar-status_${this.item.status}`],
        //         attrs: {
        //             draggable: true
        //         },
        //         on: {
        //             dragstart: this.onDrag,
        //             click: this.onClick
        //         }
        //     }, this.itemRender ? [this.itemRender(this.item)] : [h('span', this.item.text)])
        // }
    }
</script>
<style lang="less">
    @import "./variables.less";

    .schedule-calendar- {
        &detail-item {
            margin: 3px 6px 0;
            font-size: 12px;
            color: #fff;
            line-height: 2em;
            border-radius: 2px;
            background: @sc-primary-color;
            cursor: pointer;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
            transition: .2s ease-in-out;

            &:hover {
                transform: translateY(-2px);
                box-shadow: 0 3px 8px rgba(0, 0, 0, .2), 0 -3px 8px rgba(0, 0, 0, .2);
            }

            >* {
                padding: 0 5px;
            }
        }

        &status_1 {
            background: #f44336;
        }

        &status_2 {
            background: #e91e63;
        }

        &status_3 {
            background: #9c27b0;
        }

        &status_4 {
            background: #3f51b5;
        }

        &status_5 {
            background: #2196f3;
        }

        &status_6 {
            background: #00bcd4;
        }

        &status_7 {
            background: #4caf50;
        }

        &status_8 {
            background: #cddc39;
        }

        &status_9 {
            background: #ff9800;
        }

        &status_10 {
            background: #607d8b;
        }
    }
</style>
