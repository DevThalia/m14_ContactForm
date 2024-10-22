<script setup>
import { ref } from 'vue';
import formList from './formList.vue';

const nombre = ref('');
const telefono = ref('');
const contactos = ref([]);

const guardarContacto = () => {
  if (nombre.value && telefono.value) {
    contactos.value.push({
      name: nombre.value,
      telf: telefono.value
    });
    nombre.value = '';
    telefono.value = '';
  }
};
</script>

<template>
  <h1>Lista de contactos</h1>
  <div id="formContainer">
    <form id="form" @submit.prevent="guardarContacto">
      <label for="name">Nombre:</label><br>
      <input v-model="nombre" type="text" id="name" name="name" required><br><br>
      
      <label for="telf">Teléfono:</label><br>
      <input v-model="telefono" type="text" id="telf" name="telf" required><br>
      <br>
      <input type="submit" value="Guardar contacto">
    </form>
  </div>

  <div id="listContainer">
    <formList :contactos="contactos"></formList>
  </div>
</template>

<style scoped>

</style>
