<template>
  <FlexboxLayout height="50" class="calendar-weekdays">
    <Label 
      v-for="(weekday, index) in weekdays"
      :key="index"
      :text="weekday"
      class="calendar-panel__mounth" 
      width="30" 
      height="30"
    />
  </FlexboxLayout>
</template>

<script>
export default {
  props: {
    weekdays: {
      type: Array,
    },
  },
};
</script>

<style lang="scss">
  .calendar-weekdays {
    justify-content: space-between;
    align-items: center;
    background-color: rgb(236, 236, 236);
    margin-bottom: 20px;

    Label {
      color: brown;
    }
  }
</style>