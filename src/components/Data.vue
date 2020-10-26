<template>
  <div id="data" v-bind="transmissions">
    <div id="cases">
      <div id="alert">
        <img id="circle" src="../assets/alert-circle.svg" alt="">
        <h4>{{transmissions[0] > averageLastSevenDays() ? "Above" : "Below"}}<br>average</h4>
      </div>
      <div id="yesterday">
        <h1>{{addComma(transmissions[0])}}</h1>
        <h3>New Cases Yesterday</h3>
      </div>
    </div>
    <div id="evolution">
      <div class="box">
        <img src="../assets/trending-up.svg" alt="">
        <div>
          <div style="display: flex; align-items: center;">
            <span class="robotofont">{{compareTwoDays(transmissions[0],transmissions[1]) == 'increase' ? "+" : "-"}}</span><h2>{{percentageChangedLastTwoDays(transmissions[0], transmissions[1])}}%</h2>
          </div>
          <h5>{{compareTwoDays(transmissions[0],transmissions[1])}} from previous day</h5>
        </div>
      </div>
      <div class="box">
        <img src="../assets/calendar.svg" alt="">
        <div>
          <h2>{{addComma(averageLastSevenDays())}}</h2>
          <h5>Average of last 7 days</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Data",
  props: ["transmissions"],
  methods: {
    addComma(x) {
      return parseInt(x).toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
    compareTwoDays(a,b) {
      return a > b ? 'Increase' : 'Decrease';
    },
    percentageChangedLastTwoDays(a,b) {
      return Math.abs(Math.round((b - a) * 100 / b));
    },
    averageLastSevenDays() {
      return Math.round(this.transmissions.reduce((a,b) => (a + b),0) / this.transmissions.length);
    },
  }
}
</script>

<style scoped>
#data {
  margin: 90px 80px 90px 86px;
  height: 305px ;
  display: flex;
  justify-content: space-between;
}

#cases {
  background: #ffefef;
  margin-right: 35px;
  width: 515px;
  border-radius: 6px;
  -webkit-box-shadow: 0px 2px 5px -1px rgba(0,0,0,0.14);
  -moz-box-shadow: 0px 2px 5px -1px rgba(0,0,0,0.14);
  box-shadow: 0px 2px 5px -1px rgba(0,0,0,0.14);
  display: flex;
  align-items: center;
}

#alert {
  margin-left: 77px;
  margin-right: 58px;
}

#circle {
  filter: invert(19%) sepia(38%) saturate(7062%) hue-rotate(349deg) brightness(79%) contrast(101%);
  width: 60px;
}

#cases h3 {
  color: #5f5f5f;
  line-height: 50px;
}

#cases h1, h4 {
  color: #bb1515;
}

#cases h4 {
  line-height: 28px;
  font-size: 24px;
  margin-top: 2px;
}

#yesterday {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

#evolution {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.box {
  background: #fafafa;
  width: 475px;
  height: 130px;
  border-radius: 6px;
  -webkit-box-shadow: 0px 2px 8px 0px rgba(0,0,0,0.14);
  -moz-box-shadow: 0px 2px 8px 0px rgba(0,0,0,0.14);
  box-shadow: 0px 2px 8px 0px rgba(0,0,0,0.14);
  display: flex;
  align-items: center;
}

.robotofont {
  font-family: 'Roboto', sans-serif;
  font-size: 38px;
  font-weight: 900;
  color: #000000;
  margin-right: 6px;
}

.box img {
  height: 70px;
  margin-left: 82px;
  margin-right: 44px;
}

.box h5 {
  line-height: 26px;
}

@media (min-width: 960px) and (max-width: 1200px) {
  #data {
  margin: 90px 7vw 90px 7vw;
}

#cases {
  width: 43vw;
}

#alert {
  margin-left: 5vw;
  margin-right: 4vw;
}

.box {
  width: 39vw;
}

.box img {
  margin-left: 6vw;
  margin-right: 3vw;
}
}

@media (max-width: 960px) {
  #data {
  margin: 50px;
  height: 500px ;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

}

#cases {
  width: 80vw;
  margin: 0;
}

.box {
  width: 80vw;
  margin-top: 30px;
}

#alert {
  margin-left: 7vw;
  margin-right: 6vw;
}

.box img {
  margin-left: 8vw;
  margin-right: 5vw;
}
}
</style>