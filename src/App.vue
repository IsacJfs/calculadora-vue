<script setup>
import { reactive, computed } from 'vue';
import Numero from './components/Numero.vue';
import Operacao from './components/Operacao.vue';
import ValorResultado from './components/ValorResultado.vue';

const estado = reactive({
  valorUmAtual: 0,
  valorDoisAtual: 0,
  operacao: 'soma',
})

const calcular = (valorUm, valorDois, operacao) => {
  valorUm = parseFloat(valorUm);
  valorDois = parseFloat(valorDois);

  switch (operacao) {
    case 'soma': return valorUm + valorDois;
    case 'subtracao': return valorUm - valorDois;
    case 'multiplicacao': return valorUm * valorDois;
    case 'divisao': return valorUm / valorDois;
    case 'resto': return valorUm % valorDois;
    default: return 'Inválido';
  }
}
const resultado = computed(() => {
  return Math.round(calcular(estado.valorUmAtual, estado.valorDoisAtual, estado.operacao)*100)/100;
});

</script>

<template>
  <div class="container border align-content-center mt-5">
    <h1 class="text-center">Calculadora</h1>
    <div class="row justify-content-around">
      <Numero titulo="Primeiro número:" v-model="estado.valorUmAtual" />
      <Operacao v-model="estado.operacao" />
      <Numero titulo="Segundo número:" v-model="estado.valorDoisAtual" />
    </div>
    <div class="row justify-content-center mt-5">
      <ValorResultado :resultado = "resultado" />
    </div>
  </div>
</template>

<style scoped></style>
