<template>
  <div id="app">
    <pivot/>
  </div>
</template>

<script>
import pivot from "./components/pivot.vue"

export default {
  name: 'App',
  components: {
    pivot
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
  margin-top: 10px;
}
</style>
