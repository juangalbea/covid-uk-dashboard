<template>
  <div>
    <div>
      <Data :transmissions="transmissions" />
      <Chart :transmissions="transmissions" :dates="dates" v-if="transmissions.length" />
      <Rules />
    </div>
  </div>
</template>

<script>
import Data from "./Data";
import Chart from "./Chart";
import Rules from "./Rules";
export default {
  name: "Content",
  props: ["transmissions", "dates"],
  components: {
    Data,
    Chart,
    Rules,
  },
};
</script>

<style>
</style>