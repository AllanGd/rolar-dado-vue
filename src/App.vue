<template>
  <div>
    <h1>Simulador de rolagem de dados</h1>
    <dado-form></dado-form>
  </div>
</template>

<script>
import dadoForm from './components/dadoForm.vue'
export default {
  components: { dadoForm },
  

}
</script>

<style>
  * {
    color: #333;
  }
  body {
    background-color: #f5ebe0;
  }
  label {
    font-family: 'Roboto', sans-serif;
  }
</style>