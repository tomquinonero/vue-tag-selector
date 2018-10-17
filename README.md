# vue-tag-selector

[![npm bundle size (minified)](https://img.shields.io/bundlephobia/min/react.svg?style=for-the-badge)](https://github.com/tomquinonero/vue-tag-selector)
[![npm bundle size (minified + gzip)](https://img.shields.io/bundlephobia/minzip/react.svg?style=for-the-badge)](https://github.com/tomquinonero/vue-tag-selector)
[![npm version](https://img.shields.io/npm/v/vue-tag-selector.svg?style=for-the-badge)](https://github.com/tomquinonero/vue-tag-selector)



<p align="center">
  Vue-tag-selector is a component for vuejs for tag type fields. <br/>
  Light (4.4kb gzipped) and customizable.</br>
  Offering regex validation.</br></br>
  
  <img alt="vue-tag-selector demo" src="https://raw.githubusercontent.com/tomquinonero/vue-tag-selector/master/docs/tag-selector.gif">
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
 

## Related

[on Bundlephobia][link-bundlephobia] - [on npm][link-npm]

Created by [Tom Quinonero][link-author]


[link-author]: https://tomquinonero.com
[link-bundlephobia]: https://bundlephobia.com/result?p=vue-tag-selector@0.2.0
[link-npm]: https://www.npmjs.com/package/vue-tag-selector
