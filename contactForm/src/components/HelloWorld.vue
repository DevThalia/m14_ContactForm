<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div id="formContainer">
    <p>Libreta de contactos</p><br>
    <form id="form">
      <label for="name">Nombre:</label><br>
      <input type="text" id="name" name="name" required><br><br>
      
      <label for="telf">Telefono:</label><br>
      <input type="text" id="telf" name="telf" required><br>
      <br>
      <input type="submit" value="Guardar contacto">

    </form>
  </div>
</template>

<style scoped>
</style>
