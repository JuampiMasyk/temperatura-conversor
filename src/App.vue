<template>
  <div id="app">
    <h1>Conversión de Temperatura</h1>
    <div>
      <label for="celsius">Ingresa la temperatura en grados Centrígrados:</label>
      <input 
        type="number" 
        id="celsius" 
        v-model.number="celsius" 
      />
    </div>
    <div>
      <p :style="{ color: fahrenheitColor }">Fahrenheit: {{ fahrenheit }} °F</p>
      <p :style="{ color: kelvinColor }">Kelvin: {{ kelvin }} K</p>
    </div>
    <p><b>Respuestas:</b> 1:c - 2:b - 3:c - 4:a</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      celsius: 0, 
    };
  },
  computed: {
    
    fahrenheit() {
      return (this.celsius * 9/5) + 32;
    },
    
    kelvin() {
      return this.celsius + 273.15;
    },
    
    fahrenheitColor() {
      if (this.celsius <= 0) return 'blue';
      if (this.celsius > 0 && this.celsius < 15) return 'magenta';
      return 'red';
    },
    
    kelvinColor() {
      if (this.celsius <= 0) return 'blue';
      if (this.celsius > 0 && this.celsius < 15) return 'magenta';
      return 'red';
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
input {
  padding: 8px;
  margin: 10px;
  font-size: 16px;
  width: 100px;
}
</style>