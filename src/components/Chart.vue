<template>
  <div id="chart">
    <div class="size">
      <line-chart
        :width="800"
        :height="400"
        :chart-data="datacollection"
      ></line-chart>
      <button>VIEW IN DETAIL</button>
    </div>
  </div>
</template>

<script>
import LineChart from "./LineChart.js";

export default {
  name: "Chart",
  props: ["transmissions", "dates"],
  components: {
    LineChart,
  },
  data() {
    return {
      datacollection: {},
    };
  },
  mounted() {
    this.newTransmissions = [...this.transmissions];
    this.fillData();
  },
  methods: {
    fillData() {
      this.datacollection = {
        labels: this.dates.reverse(),
        datasets: [
          {
            label: "Cases per day (last 7 days)",
            backgroundColor: "#f87979",
            data: this.newTransmissions.reverse(),
          },
        ],
      };
    },
  },
};
</script>

<style>
#chart {
  background-color: #fafafa;
  margin-top: 30px;
  padding-top: 100px;
  padding-bottom: 20px;
}

.size {
  width: 900px;
  max-width: 80vw;
  margin: 50px auto;
}

button {
  margin-top: 80px;
  font-size: 11px;
  padding: 7px 36px;
  border-radius: 5px;
  text-decoration: none;
  cursor: pointer;
  color: #333333;
  background: transparent;
  border: 2px solid #4f4f4f;
  outline: none;
}

button:hover {
  color: #fafafa;
  background: transparent;
  background: #333333;
  border: 2px solid #333333;
}

@media (max-width: 960px) {
  #chart {
  margin-top: 10px;
  padding-top: 20px;
  padding-bottom: 15x;
}
}
</style>