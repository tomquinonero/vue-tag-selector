# vue-tag-selector
<p align="center">
  <img alt="vue-tag-selector logo" src="https://raw.githubusercontent.com/tomquinonero/vue-tag-selector/master/docs/tag-selector-logo.png">
<br/>
<br/>
<p><a href="https://github.com/tomquinonero/vue-tag-selector"><img src="https://img.shields.io/bundlephobia/min/react.svg?style=for-the-badge" alt="npm bundle size (minified)" /></a>
<a href="https://github.com/tomquinonero/vue-tag-selector"><img src="https://img.shields.io/bundlephobia/minzip/react.svg?style=for-the-badge" alt="npm bundle size (minified + gzip)" /></a>
<a href="https://github.com/tomquinonero/vue-tag-selector"><img src="https://img.shields.io/npm/v/vue-tag-selector.svg?style=for-the-badge" alt="npm version" /></a></p>
<br/>
<br/>
  Vue-tag-selector is a component for vuejs for tag type fields. <br/>
  Light (6.3kb gzipped) and customizable.</br>
  Offering regex validation.</br></br>
  
  <img alt="vue-tag-selector demo" src="https://raw.githubusercontent.com/tomquinonero/vue-tag-selector/master/docs/tag-selector.gif">
  <br/>
  <br/>
  <a href="http://tomquinonero.com/vue-tag-selector/" target="_blank">Check out the demo</a>
</p>



### Installation
```
# with npm
npm install --save vue-tag-selector
# with yarn
yarn add vue-tag-selector
```

### Usage
For using the component you just need to import the component and register it: 
``` js
import TagSelector from 'vue-tag-selector'
export default {
  components: { TagSelector },
  data(){
    return {
      tags: []
    }
  }
}
```

And then use it in your template:
``` html
<template>
  <div class="container">
    <tag-selector name="tags" v-model="tags"/>
  </div>
</template>
```
### API Documentation

Here's a list of the props available: 
 - `label`: Displays a label, has to be String can be ignored
 - `name`: _Required_. usually the field name.
 - `classes`: Allows you to add classes to the field. String or Array.
 - `regex`: A RegExp. Validates every tag and disallow adding if not matching. By default it's alphanumerical only (`/^[a-zA-Z0-9]*$/`)
 - `regexError`: The error displayed when the Regex doesn't match 

## Style

The component philosophy is pretty straightforward here: only the mandatory style is bundled.
I personally never liked js library that needs too much CSS. 
Only 26 lines of CSS here 😉.
But you can easily stylize the component.

Have an example template:

``` html
<div class="field tag-selector">
  <label for="tags">Post tags</label>
  <div class="tag-selector--input">
      <div class="tag-selector--item">
        Dogs <i class="icon tag-selector--remove">delete_icon</i>
      </div>
      <div class="tag-selector--item">
        Cats <i class="icon tag-selector--remove">delete_icon</i>
      </div>
      <div class="tag-selector--item">
        Horses <i class="icon tag-selector--remove">delete_icon</i>
      </div>
    <input type="text" id="tags" name="tags" class="tag-selector-input">
  </div>
  <p class="validation-message">The tag you entered is at the wrong format. Please only use alphanumerical characters.</p>
</div>
```

One rule tho, `.tag-selector--input` _has_ to be `display: flex;`.

You can see different themes applied in the [demo][link-demo]


## Related

[on Bundlephobia][link-bundlephobia] - [on npm][link-npm]

Created by [Tom Quinonero][link-author]


[link-author]: https://tomquinonero.com
[link-bundlephobia]: https://bundlephobia.com/result?p=vue-tag-selector
[link-npm]: https://www.npmjs.com/package/vue-tag-selector
[link-demo]: http://tomquinonero.com/vue-tag-selector/
