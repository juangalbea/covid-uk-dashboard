<template>
  <div id="data">
    <div id="cases">
      <div>
        <img src="" alt="">
        <h5>Above average</h5>
      </div>
      <div>
        <h1>26,688</h1>
        <h5>New Cases Yesterday</h5>
      </div>
    </div>
    <div id="evolution">
      <div class="box">
        <img src="" alt="">
        <div>
          <h2>+300%</h2>
          <p>Increase from previous day</p>
        </div>
      </div>
      <div class="box">
        <img src="" alt="">
        <div>
          <h2>17,276</h2>
          <p>Average of last seven days</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#data {
  margin: 90px 80px 90px 86px;
  height: 400px ;
  background-color: aqua;
  display: flex;
}

#cases {
  background: #ffefef;
  margin-right: 35px;
}
</style>