<script setup>
import FormComponent from './components/formComponent.vue';
</script>

<template>
  <div id="app">
    <FormComponent />
  </div>
</template>


<style scoped>
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  margin: 0;
  padding: 20px;
}

h1 {
  text-align: center;
  color: #333;
}

@media (max-width: 600px) {
  #formContainer,
  #listaContactos {
    margin: 10px;
    padding: 15px;
  }

  input[type="text"], input[type="submit"] {
    width: 100%;
  }
}

</style>
