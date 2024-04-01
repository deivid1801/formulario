<script setup>
import {reactive, ref} from 'vue'

const mostrarresultado = ref(false)
const titulo = ref('Titulo')
const produto = reactive({
  nome: 'Produto',
  preco: 19.99,
  quantidade:10,
  categorias: []
})
function formatarpreco(preco){
  return `R$ ${preco.toFixed(2).replace('.', '.')}`
}

</script>

<template>
<h1>{{ titulo }}</h1>
<div class="conteiner">
  <div class="formulario">
    <h2>Formulario</h2>
    <div class="row">
    <input type="text" v-model="titulo"/>
    <div>
    <label for="">nome</label>
    <input type="text" v-model="produto.nome"></div>
  </div>
  <div class="row">
  <div>
    <label for="">preco: </label>
    <input type="number" v-model="produto.preco"></div>
  </div>
  <div class="row">
   <label for="">quantidade</label>
   <input type="number" v-model="produto.quantidade">
  </div>
  <button @click="mostrarresultado = !mostrarresultado">Mostar</button>
  </div>
  <div class="resultado">
    <h2>Resultado</h2>
    <p>nome: {{ produto.nome }}</p>
    <p>preco: {{ formatarpreco(produto.preco) }}</p>
    <p>quantidade: {{ produto.quantidade }}</p>
    <p>categorias: {{ produto.categorias }}</p>
    <p> {{ mostrarresultado }}</p>
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
.formulario .row {
margin: 10 px auto;
width: 70%;
display: flex;
justify-content: space-between;
}
</style>
