<template>
  <div>
    <h1>Gestor de Equipos Forestales</h1>

    <ClimaZona />

    <EquipoForm
      :modoEdicion="modoEdicion"
      :equipoEditar="equipoEnEdicion"
      @guardar="guardarEquipo"
    />

    <ListaEquipos
      :equipos="equipos"
      @editar="editarEquipo"
      @eliminar="eliminarEquipo"
    />
  </div>
</template>
script>
import EquipoForm from './components/EquipoForm.vue'
import ListaEquipos from './components/ListaEquipos.vue'
import ClimaZona from './components/ClimaZona.vue'

export default {
  components: { EquipoForm, ListaEquipos,ClimaZona },
  data() {
    return {
      equipos: [],
      modoEdicion: false,
      indexEnEdicion: null,
      equipoEnEdicion: null
    }
  },
  created() {
    this.cargarDesdeLocalStorage()
  },
  methods: {
    guardarEquipo(equipo) {
      if (this.modoEdicion) {
        this.equipos.splice(this.indexEnEdicion, 1, equipo)
        this.modoEdicion = false
        this.indexEnEdicion = null
        this.equipoEnEdicion = null
      } else {
        this.equipos.push(equipo)
      }
      this.guardarEnLocalStorage()
    },
    editarEquipo(index) {
      this.modoEdicion = true
      this.indexEnEdicion = index
      this.equipoEnEdicion = { ...this.equipos[index] }
    },
    eliminarEquipo(index) {
      this.equipos.splice(index, 1)
      this.guardarEnLocalStorage()
    },
    guardarEnLocalStorage() {
      localStorage.setItem('equiposForestales', JSON.stringify(this.equipos))
    },
    cargarDesdeLocalStorage() {
      const data = localStorage.getItem('equiposForestales')
      if (data) {
        this.equipos = JSON.parse(data)
      }
    }
  }
}
</script>