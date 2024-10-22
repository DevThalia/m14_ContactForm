<script setup>
const props = defineProps({
  contactos: Array
});
</script>

<template>
  <div id="listaContactos">
    <ul>
      <li v-for="(contacto, index) in contactos" :key="index">
        <p>Nombre: {{ contacto.name }}</p>
        <p>Teléfono: {{ contacto.telf }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
</style>
