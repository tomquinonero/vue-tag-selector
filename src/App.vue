<template>
  <div id="app">
    <div class="header">
      <h1>Vue-tag-selector demo</h1>
    </div>
    <p class="hero">Here's the demo for <a href="https://github.com/tomquinonero/vue-tag-selector">vue-tag-selector</a>, 
    an amazing and light vuejs component.<br><br>
    <a href="https://github.com/tomquinonero/vue-tag-selector">vue-tag-selector on github</a> | 
    <a href="https://www.npmjs.com/package/vue-tag-selector">vue-tag-selector on npm</a>
    </p>

    <hr>

    <h2 id="styles">Using styles</h2>
    <p>The component philosophy is pretty straightforward here: only the mandatory style is bundled.<br/>
    I personally never liked js library that needs too much CSS. <br/>
    Only 26 lines of CSS here 😉.<br/>
    But you can easily stylize the component and there's examples of it:</p>
    <div class="grid-7">
      <div class="col-2 returned-values">
        <code>
          {{tags1}}
        </code>
      </div>
      <div class="col-5">
        <ol start="1">
          <li>
            <h4>No style example</h4>
            <p>The component will look like this without any style added.</p>
            <vue-tag-selector
              label="Post tags"
              v-model="tags1"
              name="tags" />
          </li>
        </ol>
      </div>
      <div class="col-2 returned-values">
        <code>
          {{tags1}}
        </code>
      </div>
      <div class="col-5">
        <ol start="2">
          <li class="theme-material">
            <h4>Material theme example</h4>
            <p>A basic material design theme. You can download the css for it <a href="https://raw.githubusercontent.com/tomquinonero/vue-tag-selector/master/src/assets/theme_material.css" target="_blank" rel="noopener noreferrer">here</a>.</p>
            <vue-tag-selector
              label="Post tags"
              v-model="tags1"
              name="tags" />
          </li>
        </ol>
      </div>
      <div class="col-2 returned-values">
        <code>
          {{tags1}}
        </code>
      </div>
      <div class="col-5">
        <ol start="3">
          <li class="theme-example">
            <h4>Look goods theme example</h4>
            <p>A home cooked colored theme. We are gonna use it for the next examples. You can download the css for it <a href="https://raw.githubusercontent.com/tomquinonero/vue-tag-selector/master/src/assets/theme_looking-good.css" target="_blank" rel="noopener noreferrer">here</a>.</p>
            <vue-tag-selector
              label="Post tags:"
              v-model="tags1"
              name="tags" />
          </li>
        </ol>
      </div>
    </div>
    <hr>
    <h2 id="styles">Regex validations</h2>
    <p>Vue-tag-selector is providing a regex props for validating tags.<br/>
    You can also specify a message for the case it fails.</p>
     <div class="grid-7">
      <div class="col-2 returned-values">
        <code>
          {{tags3}}
        </code>
      </div>
      <div class="col-5">
        <ol start="1">
          <li class="theme-example">
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
          <li class="theme-example">
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
  margin-top: 40px;
  padding: 20px;
  max-width: 800px;
  .header{
    text-align: center;
    margin-bottom: 40px;
  }
  h1{
    font-size: 32px;
    background: #faf730;
    color: #df2323;
    font-weight: bold;
    box-shadow: 5px 5px;
    animation: rotate_logo 5000ms ease infinite;
    transform-origin: 50% 50%;
    padding: 15px 10px;
    text-transform: uppercase;
    display: inline-block;
  }

  h2{
    font-size: 28px;
    background: #faf730;
    color: #df2323;
    font-weight: bold;
    box-shadow: 5px 5px;
    padding: 10px 7px;
    text-transform: uppercase;
    display: inline-block;
  }

  h4{
    margin-top: 0;
    font-style: 28px;
    text-transform: uppercase;
    color: #df2323;
    padding: 7px 0;
    padding-right: 60px;
    // background: #faf730;
    font-weight: 600;
    display: inline-block;
    // box-shadow: 5px 5px;
    border-bottom: 4px solid #df2323;
  }
  ul{
    // color: #df2323;
  }
  li{
    margin: 20px;
  }

  code{
    font-size: 18px;
    background: #e9e9e9;
    display: inline-block;
    padding: 5px;
  }
  .hero{
    font-size: 1.2em;
    font-weight: bold;
    text-align: center;
    margin-bottom: 50px;
  }
  a{
    color:#df2323;
  }
  hr{
    border: none;
    border-bottom: 3px solid #df2323;
  }
}

.theme-example{
  label{
    color: #df2323;
    font-weight: bold;
  }
  .tag-selector--input {
    border: none;
  }
  .tag-selector--item {
    background: #faf730;
    color: #df2323;
    margin-right: 8px;
    padding-left: 12px;
    font-weight: bold;
    box-shadow: 5px 5px;
    transition: 150ms all ease-in;
    transform-origin: 50% 50%;
    &:hover{
      animation: rotate_logo 400ms infinite;
    }
  }

  .tag-selector--remove {
    width: 24px;
    height: 24px;
    color: #df2323;
    line-height: 24px;
    svg{
      width: 14px;
      height: 14px;
      transition: 150ms all ease-in;
    }
    &:hover{
      svg{
        transform: scale(1.2);
        transform-origin: center center;
      }
    }
  }
  .tag-selector--item,
  .tag-selector-input {
    height: 32px;
    line-height: 32px;
    margin-bottom: 8px;
    font-size: 14px;
    color: #df2323;
    font-weight: bold;
  }
  .validation-message {
    color: #df2323;
    font-weight: bold;
    margin-top: 0;
    margin-bottom: 15px;
  }
}

@keyframes rotate_logo {
  20% {
    transform: rotate(1deg) translate3d(-3px,2px,0) perspective( 600px ) rotateY( 5deg );
  }
  
  40% {
    transform: rotate(-2deg) translate3d(1px,1px,0) perspective( 600px ) rotateY( -15deg );
  }

  60% {
    transform: rotate(2deg) translate3d(3px,-1px,0) perspective( 600px ) rotateY( 15deg );
    
  }

  80% {
    transform: rotate(-2deg) translate3d(-2px,-1px,0) perspective( 600px ) rotateY( -5deg );
  }
}

</style>
