<template>
  <FlexboxLayout height="50" class="calendar-panel">
    <Button
      @tap="prevMonth"
      text="<"
      class="calendar-panel__prev"
      width="30"
      height="30"
    />
    <Label
      class="calendar-panel__mounth"
      :text="monthName"
      width="120"
      height="30"
    />
    <Button 
      @tap="nextMont"
      text=">" 
      class="calendar-panel__next" 
      width="30" 
      height="30" 
    />
  </FlexboxLayout>
</template>

<script>
export default {
  props: {
    monthName: {
      type: String,
    },
  },
  methods: {
    prevMonth() {
      this.$emit('prevMonth');
    },
    nextMont() {
      this.$emit('nextMont')
    }
  },
};
</script>

<style lang="scss">
.calendar-panel {
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.calendar-panel__prev,
.calendar-panel__next {
  border-radius: 50%;
  font-weight: 600;
}

.calendar-panel__mounth {
  padding-top: 18px;
  text-align: center;
  font-weight: 600;
}
</style>
