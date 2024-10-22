<script setup>
import { ref,computed } from 'vue';

const props = defineProps({
  contactos: Array
})

let filter =ref('')

const contactosFiltrados=computed(()=>{
  return props.contactos.filter(contacto=>contacto.name.includes(filter.value))
})

</script>

<template>
  <div id="listaContactos"><br>
    <input v-model="filter" type="text" placeholder="Busca por nombre" />
    <ul>
      <li v-for="(contacto, index) in contactosFiltrados" :key="index">
        <p>{{ contacto.name }} - <spam style="color:red" >{{ contacto.telf }}</spam></p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
#listaContactos {
  margin: 20px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}

#listaContactos input {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 100%;
  box-sizing: border-box;
}

ul {
  list-style-type: none;
  padding: 0;
}

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

span {
  font-weight: bold;
}

span[style*="color:red"] {
  color: red;
}


</style>
