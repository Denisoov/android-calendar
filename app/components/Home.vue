<template>
  <Page>
    <StackLayout class="calendar-wrapper">
      <calendar-panel 
        @nextMont="nextMont"
        @prevMonth="prevMonth" 
        :monthName="monthName" 
      />
      <!-- <calendar-weekdays :weekdays="weekdays" /> -->
      <calendar-days 
        :days="monthDays"
        :currentDay="currentDay" 
        :nowMonth="nowMonth"
      />
    </StackLayout>
  </Page>
</template>

<script>

  import CalendarPanel from "@/components/CalendarPanel.vue";
  // import CalendarWeekdays from "@/components/CalendarWeekdays.vue"
  import CalendarDays from "@/components/CalendarDays.vue";

  export default {
    components: {
      CalendarPanel,
      // CalendarWeekdays,
      CalendarDays
    },
    data: () => ({
      nowDate: new Date(),
      currentDate: new Date(),

      monthes: ["Январь", "Февраль", "Март", "Апрель", "Май", "Июнь", "Июль", "Август", "Сентябрь", "Октябрь", "Ноябрь", "Декабрь"],
      weekdays: ["Пн", "Вт", "Ср", "Чт", "Пт", "Сб", "Вс"],

      nowMonth: new Date().getMonth(),
      nowYear: new Date().getFullYear(),
      test: null
    }),
    computed: {
      monthName() {
        return this.monthes[this.nowMonth]
      },
      currentDay() {
        return {
          day: this.currentDate.getDate(),
          month: this.currentDate.getMonth()
        }
      },
      monthDays() {
        return new Date(this.nowYear, this.nowMonth + 1, 0).getDate()
      }
    },
    methods: {
      prevMonth() {
        this.currentDate.setMonth(this.currentDate.getMonth() -1)
        this.nowMonth = this.currentDate.getMonth()
      },
      nextMont() {
        this.currentDate.setMonth(this.currentDate.getMonth() + 1)
        this.nowMonth = this.currentDate.getMonth()
      }
    },
  };
</script>

<style lang="scss">
  .calendar-wrapper {
    width: 90%;
    box-shadow: 0px 6px 37px rgba(109, 67, 90, 0.1);
    border-radius: 15px;
    margin-top: 50px;
    padding: 15px;
  }
</style>
