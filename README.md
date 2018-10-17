# vue-tag-selector

Vue-tag-selector is a component for vuejs for tag type fields. Light (4.4kb gzipped) and customizable.
Offering regex validation.


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

<p align="center">
  <a href="https://npmjs.org/package/vue-tag-selector">
    <img src="https://img.shields.io/npm/v/vue-tag-selector.svg?style=flat-square" alt="Packagist" />
  </a>

  <a href="https://github.com/tomquinonero/vue-tag-selector/issues">
    <img src="https://img.shields.io/github/issues/tomquinonero/vue-tag-selector.svg?style=flat-square" alt="Issues" />
  </a>
</p>


[on Bundlephobia][link-bundlephobia] - [on npm][link-npm]

Created by [Tom Quinonero][link-author]


[link-author]: https://tomquinonero.com
[link-bundlephobia]: https://bundlephobia.com/result?p=vue-tag-selector@0.2.0
[link-npm]: https://www.npmjs.com/package/vue-tag-selector
