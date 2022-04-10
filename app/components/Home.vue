<template>
  <Page>
    <StackLayout class="calendar-wrapper">
      <FlexboxLayout height="50" class="calendar-panel">
        <Button 
          text="<" 
          class="calendar-panel__prev"
          width="30"
          height="30"
        />
        <Label class="calendar-panel__mounth" :text="month" width="120" height="30"/>
        <Button 
          text=">"
          class="calendar-panel__next"
          width="30"
          height="30"
        />
      </FlexboxLayout>
      <Label text="second" height="70" backgroundColor="#289062"/>
      <Label text="third" height="70" backgroundColor="#1c6b48"/>
    </StackLayout>
  </Page>
</template>

<script>
  export default {
    data: () => ({
      typeChart: 'lastMounth',
      nowDay: new Date().getDate(),
      nowMonth: new Date().getMonth(),
      nowYear: new Date().getFullYear(),
      selectedDay: new Date().getDate(),
      month: new Date().getMonth(),
      year: new Date().getFullYear(),
      monthes: ["Январь", "Февраль", "Март", "Апрель", "Май", "Июнь", "Июль", "Август", "Сентябрь", "Октябрь", "Ноябрь", "Декабрь"],
      date: new Date(),
    })
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
