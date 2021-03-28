<template>
  <div id="app">
    <Header v-bind:title="location"></Header>
    <Forecast></Forecast>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Forecast from './components/Forecast.vue';

export default {
  name: 'App',
  components: {
    Header,
    Forecast
  },
  data() {
    return {
      location: 'Budapest'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
