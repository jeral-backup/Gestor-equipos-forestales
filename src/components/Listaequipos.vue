<template>
  <ul>
    <li v-for="(equipo, index) in equipos" :key="index">
      {{ equipo.tipo }} - {{ equipo.estado }} - {{ equipo.fecha }}
      <button @click="$emit('editar', index)">Editar</button>
      <button @click="$emit('eliminar', index)">Eliminar</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['equipos']
};
</script>
