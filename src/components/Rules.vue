<template>
  <div id="rules">
    <div class="rule">
      <h2>WASH HANDS</h2>
      <p>Keep washing your<br>hands regularly</p>
    </div>
    <div class="rule">
      <h2>COVER FACE</h2>
      <p>Wear a face covering<br>in enclosed spaces</p>
    </div>
    <div class="rule">
      <h2>MAKE SPACE</h2>
      <p>Stay at least 2 meters<br>apart, wear face covering</p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#rules {
  display: flex;
  justify-content: space-evenly;
  margin: 150px 70px;
}

.rule {
  width: 260px;
}

h2 {
  font-size: 29px;
  margin-bottom: 14px;
}

p {
  color: #505050;
  line-height: 18px;
}

@media (min-width: 960px) and (max-width: 1200px) {
  #rules {
    margin: 150px 9vw;
    max-width: 86vw;
  }

  .rule {
    width: 26rem;
  }
}

@media (max-width: 960px) {
  #rules {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 20px 0 60px 0;
}

.rule {
  width: 80vw;
  margin-top: 50px;
}

h2 {
  font-size: 50px;
  margin-bottom: 14px;
}

p {
  color: #505050;
  font-size: 20px;
  line-height: 30px;
}
}
</style>