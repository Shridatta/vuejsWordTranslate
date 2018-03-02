<template>
  <div id="app">
   <h1> Word Translator </h1>
   <TranslateForm v-on:formSubmit="translateText"/>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
export default {
  name: 'App',
  components: {
    TranslateForm
  },
  methods:
  {
    translateText: function(text){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180302T031807Z.fb5815557a96c863.1511680e19ff6834c42242f780b8fc6b214f01ed&lang=es&text='+text)
      .then((response)=>{
        console.log(response);
      });
    }
  }
}
</script>

<style>
#app {

}
</style>
