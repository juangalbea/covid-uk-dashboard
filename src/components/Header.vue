<template>
  <div id="header">
    <div id="title">
      <h1>COVID UK</h1>
      <p>
        Use this tool to find out the latest stats for the Coronavirus in the UK
      </p>
    </div>
    <arrow-down-icon size="1.8x" class="custom-class arrow"></arrow-down-icon>
  </div>
</template>

<script>
import { ArrowDownIcon } from "vue-feather-icons";
export default {
  components: {
    ArrowDownIcon,
  },
};
</script>

<style scoped>
#header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: url("../assets/pandemic2.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  height: 520px;
  color: white;
  margin: 0;
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

@media (min-width: 960px) and (max-width: 1200px) {
  #header {
    max-width: 100vw;
    width: 100vw;
  }

  #title {
    margin-left: 100px;
    max-width: 60vw;
  }
}

@media (max-width: 960px) {
  #header {
    max-width: 100vw;
  }
  
  #title {
    width: 50vw;
    margin: 2px;
    min-width: 340px;
  }

  .arrow {
    display: none;
  }

  #title p {
    width: 280px;
    line-height: 30px;   
    margin: 20px; 
  }

  #title {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 866px;
  margin: 167px;
  max-width: 80vw;
}
}
</style>