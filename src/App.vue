<template>
  <div id="app">
    <h1>Vue tage selector</h1>
    <p>Vue tag selector is a form component written with vue 
      (duh) and allows you to create tag seleciton like field.</p>
    <p>The goal is to use a v-model property on the component that 
      will return an array of the tags entered</p>
    <h2>Documentation</h2>
    <h2>Examples</h2>
    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
