<template>
  <div id="app">
    <advice/>
  </div>
</template>

<script>
import Advice from './components/Advice.vue'

export default {
  name: 'App',
  components: {
    Advice
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
