<template>
  <div id="TranslateForm">
   <h1> TranslateForm </h1>
   <form v-on:submit="formSubmit">
    <input type="text" v-model="textToTranslate" placeholder="enter a text">
    <select v-model="language">
      <option value='es'>Spanish</option>
      <option value='ja'>Japanese</option>
      <option value='hi'>Hindi</option>
      <option value='mr'>Marathi</option>
    </select>
    <input type='submit' value='Translate'>
   </form>
  </div>
</template>

<script>
export default {
  name: 'TranslateForm',
  data(){
    return {
      textToTranslate: '',
      language: ''
    }
  },
  created(){
    this.language='es';
  },
  methods:{
    formSubmit(e)
  {
    this.$emit('formSubmit',this.textToTranslate,this.language);
    e.preventDefault();
  }
}
}
</script>

<style>

</style>
