<template>
  <div id="app">
    <h1>hola mundo</h1>
    <input type="text" v-model="name" placeholder="ingrese nombre">
    <button @click="generar">generar</button>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import jspdf from 'jspdf'

export default {
  name: "App",
  methods:{
    generar(){
      const doc = new jspdf()
      doc.text(this.name,15,15)
      doc.save("nombres.pdf")
    }
  },
  components: {
    HelloWorld
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
