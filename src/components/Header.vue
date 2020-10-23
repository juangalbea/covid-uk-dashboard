<template>
  <div id="header">
    <div id="title">
      <h1>COVID UK</h1>
      <p>Use this tool to find out the latest stats for the Coronavirus in the UK</p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  margin: 0;
  background: url('../assets/pandemic2.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  height: 520px;
  color: white;
}

#title {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  margin: 167px;
}

h1 {
  line-height: 100px;
}


</style>