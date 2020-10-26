<template>
  <div>
    <div v-bind="transmissions">
      <Data v-bind:transmissions="transmissions" />
      <!-- <Chart /> -->
      <Rules />
    </div>
  </div>
</template>

<script>
import Data from "./Data";
// import Chart from "./Chart";
import Rules from "./Rules";
export default {
  name: "Content",
  props: ["transmissions"],
  components: {
    Data,
    // Chart,
    Rules,
  },
};
</script>

<style>
</style>