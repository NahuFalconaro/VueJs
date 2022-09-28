<template>
  <ComponentePadre></ComponentePadre>
</template>

<script>
import ComponentePadre from './components/ComponentePadre.vue'

export default {
  name: 'App',
  components: {
    ComponentePadre
},data(){
  return{
    mensaje: 'Mensaje desde attr'
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
