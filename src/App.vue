<template>
  <div id="app">
    <h1>Vue tag selector demo</h1>
    <vue-tag-selector
      label="Post tags"
      v-model="tags"
      name="tags" />
    <br/>
    Tags: {{tags.join(', ')}}
    <br/>
    <br/>
    
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
import VueTagSelector from './components/VueTagSelector'
import './assets/theme_material.css'

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
