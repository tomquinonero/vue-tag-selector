<template>
  <div id="app">
    <h1>Vue tage selector</h1>
    <p>Vue tag selector is a form component written with vue 
      (duh) and allows you to create tag seleciton like field.</p>
    <p>The goal is to use a v-model property on the component that 
      will return an array of the tags entered</p>
    <h2>Documentation</h2>
    <h2>Examples</h2>
    <h3>No style</h3>
    <vue-tag-selector
      label="Post tags"
      v-model="tags"
      name="tags" />
    <pre>
      {{tags}}
    </pre>
    <h3>Material theme</h3>
    <div class="theme-material">
      <vue-tag-selector
      label="Post tags"
      v-model="tags"
      name="tags"/>
    </div>
    <pre>
      {{tags}}
    </pre>
  </div>
</template>

<script>
import VueTagSelector from './components/VueTagSelector.vue'

export default {
  name: 'app',
  data(){
    return{
      tags: []
    }
  },
  components: {
    VueTagSelector
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
  margin: 0 auto;
  margin-top: 60px;
  padding: 20px;
  max-width: 650px;
}
</style>
