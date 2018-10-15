<template>
  <div class="field tag-list" :class="classes">
    <label :for="name">{{label}} <em class="optional" v-if="optional">optional</em></label>
    <div class="tag-list--input">
      <div class="tag-list--item" v-for="(item, index) in newValue" :key="index">
        {{item}} 
        <i class="icon tag-list--remove" @click="removeTag(index)">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M12 2C6.47 2 2 6.47 2 12s4.47 10 10 10 10-4.47 10-10S17.53 2 12 2zm5 13.59L15.59 17 12 13.41 8.41 17 7 15.59 10.59 12 7 8.41 8.41 7 12 10.59 15.59 7 17 8.41 13.41 12 17 15.59z"/></svg>
        </i>  
      </div>
      <input @keyup.enter.prevent="addTag" 
      @keyup.space="addTagKey" 
      @keyup.188="addTagKey" 
      @keyup.8="handleBackspace" 
      v-model="tag" 
      type="text" 
      :id="name" 
      :name="name" 
      :placeholder="placeholder" 
      class="tag-list-input">
    </div>
    <p v-if="error" class="validation-message">{{$t(error)}}</p>
  </div>
</template>
<script>
export default{
  name: 'vue-tag-selector',
  props: {
    label: String,
    name: String,
    value: Array,
    classes: String,
    optional: Boolean,
    regex: RegExp,
    regexError: String
  },
  data(){
    return{
      newValue: Array,
      error: "",
      tag: "",
      backspace_count: 1,
      suggestions: []
    }
  },
  methods:{
    checkSuggestion(){
      this.suggestions = ['Suggestion 1','Cool tag','One more']
    },
    handleBackspace(){
      if(this.tag == ""){
        if(this.backspace_count == 0){
          this.backspace_count++
        }else{
          this.removeLastTag()
        }
      }else{
        this.backspace_count = 0
      }
    },
    removeLastTag(){
      let index = this.newValue.length - 1
      this.removeTag(index)
    },
    removeTag(index){
      this.newValue.splice(index,1)
    },
    validate(tag){
      return this.regex.test(tag)
    },
    addTagKey(){
      let tag = this.tag
      this.tag = tag.substring(0, tag.length-1)
      this.addTag()
    },
    addTag(){
      if(this.newValue === undefined){
        this.newValue = []
      }
      if(this.tag != ''){
        if(this.validate(this.tag)){
          this.newValue.push(this.tag)
          this.tag = ""
          this.error = ""
        }else{
          this.error = this.regexError
        }
      }
    }
  },
  created () {
    this.newValue = this.value
  },
  watch: {
    value() {
      this.newValue = this.value
    },
    newValue () {
      this.$emit('input', this.newValue)
    }
  }
}
</script>
<style lang="scss" scoped>
*{
  box-sizing: border-box;
}

label{
  margin-bottom: 8px;
  display: block;
}
.tag-list--input{
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-content: flex-start;
}
.tag-list--item{
  margin: 0;
  padding: 0;
  user-select: none;
}
.tag-list--remove{
  display: inline-block;
  vertical-align: text-top;
  vertical-align: middle;
  cursor: pointer;
  svg{
    fill: currentColor;
  }
}
.tag-list-input{
  margin-bottom: 0;
  min-width: 80px;
  border:none;
  outline: none;
  flex-grow: 1;
  background: transparent;
}


.theme-material{
  .tag-list--input{
    border-bottom: 1px dotted #959595;
    margin-bottom:1.2em;
  }
  .tag-list--item{
    background: #e6e6e6;
    color: #434343;
    margin-right: 8px;
    padding-left: 12px;
    border-radius: 32px;
    &:hover{
      background: #434343;
      color: #fafafa;
      .tag-list--remove{
        color: #fafafa;
      }
    }
  }

  .tag-list--remove{
    width: 24px;
    height: 24px;
    color: #434343;
    margin: 4px 4px; 
  }
  .tag-list--item,
  .tag-list-input{
    height: 32px;
    line-height: 32px;
    margin-bottom: 8px;
    font-size: 14px;
  }
  .validation-message{
    color: #a90014;
  }
}
</style>
