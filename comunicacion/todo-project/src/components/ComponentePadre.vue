<template>
  <ComponenteHijo v-bind:msj="mensajePadre" @mensajeDesdeHijo="mandarMensaje"></ComponenteHijo>
  <!-- @nombre de primer variable de $emit, seria v-on:nombre de primer variable en $emit-->
  <!-- <ComponenteHijo msj="estoy mandando mensaje" ></ComponenteHijo> -->
  <p>{{msjHijo}}</p>
</template>

<script>
import ComponenteHijo from './ComponenteHijo.vue'
export default {
    name: 'ComponentePadre',
    components: {
      ComponenteHijo,
  },
  data(){
    return{
      mensajePadre: 'Mensaje desde attr mensaje de padre a hijo',
      msjHijo: ' '
    }
  },
  methods:{
    mandarMensaje(arg1){
      this.msjHijo = arg1;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
