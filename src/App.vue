<script setup>
import { reactive } from 'vue';
import Operacao from './components/Operacao.vue'
import Resultado from './components/Resultado.vue'

const estado = reactive({
  operacao: '+',
  numero1: '',
  numero2: ''
})


const resultado = () => {
  const {operation} = estado
  switch(operation){
    case '-':
    return parseFloat(estado.numero1) - parseFloat(estado.numero2)
    case '*':
    return parseFloat(estado.numero1) * parseFloat(estado.numero2)
    case '/':
    return parseFloat(estado.numero1) / parseFloat(estado.numero2)
    default: 
    return parseFloat(estado.numero1) + parseFloat(estado.numero2)
  }
} 

</script>

<template>
  <div class="container p-3 mb-2 bg-primary text-white text-center">
    <h1>Calculadora</h1>
    <Operacao :operacao="evento => estado.operation = evento.target.value" 
    :numero1="evento => estado.numero1 = evento.target.value"
    :numero2="evento => estado.numero2 = evento.target.value"/>
    <Resultado :numero1="estado.numero1" :numero2="estado.numero2" :resultado="resultado()"/>
  </div>
</template>

<style></style>

