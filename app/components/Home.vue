<template>
  <Page>
    <StackLayout class="calendar-wrapper">
      <calendar-panel :monthName="monthName" />
      <calendar-weekdays :weekdays="weekdays" />
      <Label text="third" height="70" backgroundColor="#1c6b48"/>
    </StackLayout>
  </Page>
</template>

<script>

  import CalendarPanel from "@/components/CalendarPanel.vue";
  import CalendarWeekdays from "@/components/CalendarWeekdays.vue"

  export default {
    components: {
      CalendarPanel,
      CalendarWeekdays
    },
    data: () => ({
      nowDate: new Date(),
      currentDate: new Date(),

      monthes: ["Январь", "Февраль", "Март", "Апрель", "Май", "Июнь", "Июль", "Август", "Сентябрь", "Октябрь", "Ноябрь", "Декабрь"],
      weekdays: ["Пн", "Вт", "Ср", "Чт", "Пт", "Сб", "Вс"],

      nowMonth: new Date().getMonth(),
      nowYear: new Date().getFullYear(),
    }),
    computed: {
      monthName() {
        return this.monthes[this.nowMonth]
      },
      monthDays() {
        return new Date(this.nowYear, this.nowMonth + 1, 0).getDate()
      }
    },
    methods: {
      prevMonth() {
        this.currentDate.setMonth(this.currentDate.getMonth() -1)
      }
    },
  };
</script>

<style lang="scss">
  .calendar-wrapper {
    .calendar-panel {
      align-items: center;
      justify-content: center;
    }
    .calendar-panel__prev, .calendar-panel__next {
      border-radius: 50%;
      font-weight: 600;
    }
    .calendar-panel__mounth {
      padding-top: 18px;
      text-align: center;
    }
  }
</style>
