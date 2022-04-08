<template>
    <Page>
    <ActionBar :title="title">
      <NavigationButton text="Back" ></NavigationButton>
    </ActionBar>
    <RadCalendar></RadCalendar>
  </Page>
</template>

<script>

  export default {

  };
</script>

<style scoped lang="scss">
    @import '@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
