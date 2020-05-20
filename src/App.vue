<template>
  <div id="app">
    <General/>
  </div>
</template>

<script>
import General from './components/General.vue'

export default {
  name: 'App',
  components: {
    General
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
  background-color: #eeeeee;
  height: 100%;
}

html, body {
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
