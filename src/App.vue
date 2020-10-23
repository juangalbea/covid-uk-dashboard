<template>
  <div id="app">
    <Header />
    <Content />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';
import Content from './components/Content';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Content
  }
}
</script>

<style>
h1 {
  font-size: 80px;
  font-family: 'Roboto Condensed', sans-serif;
  font-weight: bold;
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
</style>
