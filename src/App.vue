<template>
  <div id="app">
    <h1>Vue tag selector demo</h1>
    <p>Here"s the demo for <a href="https://github.com/tomquinonero/vue-tag-selector">vue-tag-selector</a>, 
    an amazing and light vuejs component.</p>
    <div class="grid-7">
      <div class="col-2 returned-values">
        <code>
          {{tags1}}
        </code>
      </div>
      <div class="col-5">
        <ol start>
          <li>
            <h4>Basic example</h4>
            <vue-tag-selector
              label="Post tags"
              v-model="tags1"
              name="tags" />
          </li>
          <li class="theme-material">
            <h4>Material theme example</h4>
            <vue-tag-selector
              label="Post tags"
              v-model="tags1"
              name="tags" />
          </li>
          <li class="theme-example">
            <h4>Look goods theme example</h4>
            <vue-tag-selector
              label="Post tags"
              v-model="tags1"
              name="tags" />
          </li>
        </ol>
      </div>
    </div>
    <hr>
    <h2>Regex validations</h2>
     <div class="grid-7">
      <div class="col-2 returned-values">
        <code>
          {{tags3}}
        </code>
      </div>
      <div class="col-5">
        <ol start="1">
          <li>
            <h4>Only lowercase</h4>
            <vue-tag-selector
              label="Add friends with their username:"
              v-model="tags3"
              name="tags" 
              :regex="/^[a-z_\-]*$/g" 
              regex-message="The username must only contains lowercase letter and underscores."/>
          </li>
        </ol>
      </div>
    <div class="col-2">
      <code>
        {{tags2}}
      </code>
    </div>
    <div class="col-5">
        <ol start="5">
          <li>
            <h4>Only email addresses</h4>
            <vue-tag-selector
              label="Send mail notifications to:"
              v-model="tags2"
              name="tags"
              :regex="/^\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$/g"
              regex-message="The email fromat is invalid."/>
          </li>
        </ol>
    </div>
    </div>
    
    <br/>
    <br/>
  </div>
</template>

<script>
import VueTagSelector from './components/VueTagSelector'
import './assets/theme_material.css'
import './../node_modules/knacss/css/grillade-grid.css'

export default {
  name: 'app',
  data(){
    return{
      tags1: ["Blog", "High-Tech", "Vuejs", "#twitter"],
      tags2: ["tom@gmail.com", "support@example.com", "notify@service.net"],
      tags3: ["blog", "high_tech"],
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
  color: #2c3e50;
  margin: 0 auto;
  margin-top: 60px;
  padding: 20px;
  max-width: 800px;
  h1{
    font-size: 24px;
  }
}

.theme-example{

}
</style>
