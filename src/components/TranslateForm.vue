<template>
  <div id="TranslateForm">
   <h1> TranslateForm </h1>
   <form v-on:submit="formSubmit">
    <input type="text" v-model="textToTranslate" placeholder="enter a text">
    <input type='submit' value='Translate'>
   </form>
  </div>
</template>

<script>
export default {
  name: 'TranslateForm',
  data(){
    return
    {
      textToTranslate: ''
    }
  },
  methods:{
    formSubmit(e)
  {
    this.$emit('formSubmit',this.textToTranslate);
    e.preventDefault();
  }
}
}
</script>

<style>

</style>
