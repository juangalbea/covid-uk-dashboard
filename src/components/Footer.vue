<template>
  <div id="footer">
      <div>
        <p>An RCCO development challenge by JUAN GARCIA ALBEA</p><br><p>Data source: Gov.uk</p>
      </div>
      <h3>COVID UK</h3>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
  background-color: #1c4155;
  height: 120px;
  padding-left: 95px;
  padding-right: 75px;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
  max-width: 95vw;
}

#footer div {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

#footer p {
  line-height: 8px;
}

#footer h3 {
  margin-top: 10px;
}

@media (max-width: 960px) {
  #footer {
  flex-direction: column;
  justify-content: space-evenly;
  height: 220px;
}

#footer p {
  line-height: 20px;
}
}
</style>