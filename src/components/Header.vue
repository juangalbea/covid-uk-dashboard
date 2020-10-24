<template>
  <div id="header">
    <div id="title">
      <h1>COVID UK</h1>
      <p>Use this tool to find out the latest stats for the Coronavirus in the UK</p>
    </div>
    <arrow-down-icon size="1.8x" class="custom-class arrow"></arrow-down-icon>
  </div>
</template>

<script>
import { ArrowDownIcon } from 'vue-feather-icons'
export default {
  components: {
    ArrowDownIcon
  }
}
</script>

<style scoped>
#header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
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
  width: 866px;
  margin: 167px;
}

h1 {
  margin-top: 20px;
  line-height: 100px;
}

.arrow {
  cursor: pointer;
  color: #828282;
}

.arrow:hover {
  color: white;
}
</style>