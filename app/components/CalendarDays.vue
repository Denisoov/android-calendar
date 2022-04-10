<template>
  <FlexboxLayout height="auto" class="calendar-days">
    <Label
      v-for="(day, index) in days"
      :key="index"
      :text="day"
      class="calendar-panel__mounth"
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
  },
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
    padding-top: 30px;
    margin-left: 10px;
    margin-bottom: 15px;
    border-radius: 50%;
  }
}
</style>
