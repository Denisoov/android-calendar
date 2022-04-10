<template>
  <FlexboxLayout height="auto" class="calendar-days">
    <Label
      v-for="(day, index) in days"
      :key="index"
      :text="day"
      class="calendar-panel__mounth"
      :style="{
        'background-color': checkCurrentDay(index)
      }"
      width="44"
      height="44"
    />
  </FlexboxLayout>
</template>

<script scoped>
export default {
  props: {
    days: {
      type: Array,
    },
    currentDay: {
      type: Object
    },
    nowMonth: {
      type: Number
    },
  },
  methods: {
    checkCurrentDay(index) {
      return index + 1 === this.currentDay.day && this.nowMonth === this.currentDay.month 
        ? '#93dbf1' 
        : '#f3f3f3'
    }
  }
};
</script>

<style lang="scss">
.calendar-days {
  width: 100%;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-content: flex-start;

  Label {
    background-color: #f3f3f3;
    text-align: center;
    padding-top: 36px;
    margin-left: 10px;
    margin-bottom: 15px;
    border-radius: 50%;
  }
}
</style>
