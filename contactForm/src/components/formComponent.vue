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
/* Estilos generales de la aplicación */
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  margin: 0;
  padding: 20px;
}

/* Estilos para el título */
h1 {
  text-align: center;
  color: #333;
}

/* Estilos para el contenedor del formulario */
#formContainer {
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #fff;
  max-width: 400px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Estilos para el formulario */
#form {
  display: flex;
  flex-direction: column;
}

/* Estilos para las etiquetas */
label {
  margin-bottom: 5px;
  font-weight: bold;
  color: #333;
}

/* Estilos para los inputs de texto */
input[type="text"] {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-bottom: 15px;
  font-size: 16px;
}

/* Estilos para el botón de enviar */
input[type="submit"] {
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s;
}

input[type="submit"]:hover {
  background-color: #0056b3;
}

/* Estilos para el contenedor de la lista de contactos */
#listContainer {
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #fff;
  max-width: 400px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Estilos para la lista de contactos */
#listaContactos {
  margin-top: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

/* Estilos para cada elemento de la lista */
li {
  padding: 10px;
  border-bottom: 1px solid #ddd;
}

li:last-child {
  border-bottom: none;
}

li p {
  margin: 0;
}

/* Estilos para el texto de teléfono */
span {
  font-weight: bold;
}

span[style*="color:red"] {
  color: red;
}

/* Responsividad */
@media (max-width: 600px) {
  #formContainer,
  #listContainer {
    margin: 10px;
    padding: 15px;
    max-width: 90%;
  }

  input[type="text"], input[type="submit"] {
    width: 100%;
  }
}
</style>
