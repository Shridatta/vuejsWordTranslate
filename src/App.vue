<template>
  <div id="app">
   <h1> Word Translator </h1>
   <TranslateForm v-on:formSubmit="translateText"/>
   <translatedOutput v-text="translatedText" />
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import translatedOutput from './components/translatedOutput'
export default {
  name: 'App',
  components: {
    TranslateForm,
    translatedOutput
  },
  data: function()
  {
    return{
      translatedText:''
    }
  },
  methods:{
    translateText: function(text,language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180302T031807Z.fb5815557a96c863.1511680e19ff6834c42242f780b8fc6b214f01ed&lang='+language+'&text='+text)
      .then((response)=>{
      this.translatedText = response.body.text[0];
      });
    }
  }
}
</script>

<style>
#app {

}
</style>
