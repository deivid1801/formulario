<script setup>
import {ref} from 'vue'

const titulo = ref('Titulo')
</script>

<template>
<h1>{{ titulo }}</h1>
<div class="conteiner">
  <div class="formulario">
    <h2>Formulario</h2>
    <input type="text" v-model="titulo"/>
  </div>
  <div class="resultado">
    Resultado
  </div>
</div>
</template>

<style scoped>
.container{
  gap: 1.5rem;
  display: flex;
  flex-direction: row;
  width: 100vw;
}
.formulario,
.resultado{
  width: 45%;
  border-radius: 10px;
  padding: 10px;
  justify-content: center;
}
.formulario{
  background-color: darkcyan;
}
.resultado{
  background-color: coral;
}
</style>
