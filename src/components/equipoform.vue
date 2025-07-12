<template>
  <form @submit.prevent="guardarEquipo">
    <input v-model="equipo.tipo" placeholder="Tipo de equipo" required />
    <input v-model="equipo.estado" placeholder="Estado (activo/mantenimiento)" required />
    <input v-model="equipo.fecha" type="date" required />
    <button type="submit">{{ modoEdicion ? 'Actualizar' : 'Agregar' }}</button>
  </form>
</template>

<script>
export default {
  props: ['modoEdicion', 'equipoEditar'],
  data() {
    return {
      equipo: {
        tipo: '',
        estado: '',
        fecha: ''
      }
    };
  },
  watch: {
    equipoEditar(newVal) {
      if (newVal) this.equipo = { ...newVal };
    }
  },
  methods: {
    guardarEquipo() {
      this.$emit('guardar', { ...this.equipo });
      this.equipo = { tipo: '', estado: '', fecha: '' };
    }
  }
};
</script>
