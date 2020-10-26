<template>
  <div id="app">
    <Header />
    <Content :transmissions="transmissions" :dates="dates" />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";
import Content from "./components/Content";
import axios from 'axios';

export default {
  name: "App",
  components: {
    Header,
    Footer,
    Content,
  },
  data() {
    return {
      transmissions: [],
      dates: []
    }
  },
  methods: {

  },
  created() {
    axios.get('https://api.coronavirus.data.gov.uk/v1/data?' +
    'filters=areaType=nation;areaName=england&' +
    'structure={"date":"date","newCases":"newCasesByPublishDate"}')
      .then(res => {
        const data = res.data.data.slice(0, 7);
        const persons = []
        const time = []
        for (let key in data) {
          const person = data[key]
          persons.push(person.newCases)
          const day = person.date.split("-")
          day.shift();
          const day1 = day.reverse().join("/")
          time.push(day1)
        }
        this.transmissions = persons
        this.dates = time
      })
      .catch((err) => console.log(err));
  }
};
</script>

<style>
html, body {
  margin: 0; 
  padding: 0;
  overflow-x: hidden;
  }

h1 {
  font-size: 80px;
  font-family: "Roboto Condensed", sans-serif;
  font-weight: bold;
}

h2 {
  font-size: 56px;
  font-family: "Roboto Condensed", sans-serif;
  font-weight: bold;
  color: #000000;
}

h3 {
  font-family: "Roboto Condensed", sans-serif;
  font-weight: bold;
  font-size: 24px;
}

h4 {
  font-weight: bold;
  font-family: "Roboto Condensed", sans-serif;
}

h5 {
  font-weight: bold;
  font-family: "Roboto Condensed", sans-serif;
  color: #5f5f5f;
}

/* p {
  font-family: 'Roboto', sans-serif;
} */

#app {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 1200px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

@media (max-width: 1200px) {
  #app {
    width: 100vw;
  }
}
</style>
