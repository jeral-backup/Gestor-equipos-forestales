<template>
  <div v-if="clima">
    <h2>Clima actual en Biobío 🌤️</h2>
    <p>Temperatura: {{ clima.temperature }}°C</p>
    <p>Viento: {{ clima.windspeed }} km/h</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clima: null
    }
  },
  mounted() {
    fetch('https://api.open-meteo.com/v1/forecast?latitude=-37.5&longitude=-72.5&current_weather=true')
      .then(response => response.json())
      .then(data => {
        this.clima = data.current_weather
      })
      .catch(error => console.error('Error al cargar el clima:', error))
  }
}
</script>
