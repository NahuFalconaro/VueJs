<template>
  <h2>ComponenteHijo</h2>
  <p>{{msj}}</p>
  <!-- <input v-model="msjHijo"> -->
  <button @click="mandarMensaje()">enviar mensaje desde hijo a padre</button>
</template>

<script>
export default {
  name: 'ComponenteHijo',
  props: {
    msj: String
  },
  data(){
    return{
      msjHijo:'mensaje desde hijo a padre al apretar el boton'
    }
  },
  methods:{
    mandarMensaje(){
      this.$emit('mensajeDesdeHijo', this.msjHijo)
      //this.$emit('mensajeDesdeHijo', this.msjHijo,'Segundo parametro', 'tercer parametro')
    }//primer parametro, le pasa el nombre que relaciona?
  }
}
</script>
