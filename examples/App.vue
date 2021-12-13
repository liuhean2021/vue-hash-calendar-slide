<template>
  <div class="body">
    <vue-hash-calendar-slide ref="picker"
                       model="inline"
                       :scroll-change-date="true"
                       :visible.sync="isShowCalendar"
                       :default-datetime="defaultDatetime"
                       :is-show-week-view="false"
                       :minute-step="1"
                       :bottomTextFlag="false"
                       :mark-date="markDate"
                       :disabled-date="disabledDate"
                       week-start="sunday"
                       picker-type="datetime"
                       :show-today-button="true"
                       :disabled-week-view="false"
                       :mainBackgroundColor="'white'"
                       :disableColor="'#c0c4cc'"
                       :borderBoxShadow="'0 5px 10px 0px rgba(203,203,203,0.5)'"
                       :borderRadius="'5px'"
                       :contentColor="'#333333'"
                       :circleBackgroundColor="'#0F8EE9'"
                       :calendarWeekColor="'#999999'"
                       :scroll-change-date-remember-date="false"
                       :showArrowIcon="true"
                       format="YY/MM/DD hh:mm"
                       lang="CN"
                       @confirm="dateConfirm"
                       @click="dateClick"
                       @change="dateChange"
                       @height="heightChange">
    </vue-hash-calendar-slide>
  </div>
</template>

<script>

export default {
  name: 'demo',
  data() {
    return {
      isShowCalendar: true, // 是否显示弹窗
      isShowTips: false, // 是否显示下载提示
      defaultDatetime: new Date(),
      markDate: [
        { color: 'rgba(187,27,27,0.3)', type: 'background', date: ['2020/02/25', '2020/03/25', '2020/04/25', '2020/05/25', '2020/06/25', '2020/07/25', '2020/08/25', '2020/09/25', '2020/10/25', '2020/11/25', '2020/12/25', '2021/12/01', '2021/12/02', '2021/11/30'] },
        { color: '#2c0bc2', type: 'dateColor', date: ['2020/02/26', '2020/03/26', '2020/04/26', '2020/05/26', '2020/06/26', '2020/07/26', '2020/08/26', '2020/09/26', '2020/10/26', '2020/11/26', '2020/12/29', '2021/12/01', '2021/12/02', '2021/11/30'] },
        { color: '#ff0000', type: 'dot', date: ['2020/01/20', '2020/02/20', '2020/03/20', '2020/04/20', '2020/05/20', '2020/06/20', '2020/07/20', '2020/08/20', '2020/09/20', '2020/10/20', '2020/11/20', '2020/12/20', '2021/11/29', '2021/12/01', '2021/12/02', '2021/11/30'] },
        { color: '#133fcf', type: 'topRightIcon', date: ['2020/01/12', '2020/02/12', '2020/03/12', '2020/04/12', '2020/05/12', '2020/06/12', '2020/07/12', '2020/08/12', '2020/09/12', '2020/10/12', '2020/11/12', '2020/12/12', '2021/12/01', '2021/12/02', '2021/11/30'] },
        { color: '#b7bc1f', text: '节假日', type: 'bottomText', date: ['2020/01/29', '2020/02/29', '2020/03/29', '2020/04/29', '2020/05/29', '2020/06/29', '2020/07/29', '2020/08/29', '2020/09/29', '2020/10/29', '2020/11/29', '2020/12/29', '2021/12/01', '2021/12/02', '2021/11/30'] }
      ], // 对象数组形式的标记日期，可以自定义标记颜色
      calendarHeight: 0
    }
  },
  watch: {
    calendarHeight: function(n, o) {

    }
  },
  methods: {
    showCalendarDialog() { // 显示日历
      this.isShowCalendar = true
    },
    dateChange(date) { // 日期改变触发
      console.log(date, 'change')
    },
    dateConfirm(date) { // 点击确认按钮触发
      console.log(date, 'confirm')
    },
    dateClick(date) { // 点击日期时按钮触发
      console.log(date, 'click')
    },
    disabledDate(date) { // 禁用的日期
      return false
      // let timestamp = date.getTime()
      // let oneDay = 24 * 60 * 60 * 1000
      //
      // if (timestamp < new Date().getTime() - oneDay) {
      //   return true
      // }
      //
      // return false
    },
    heightChange(height) {
      this.calendarHeight = height
      this.$emit('height', height)
    }
  }
}
</script>
