<script setup>
import { reactive } from 'vue';

const estado = reactive({
  valorUmAtual: 0,
  valorDoisAtual: 0,
  operacao: 'soma',
})

const resultado = () => {
  const {operacao} = estado;

  switch (operacao) {
    case 'soma':
      const resultadoSoma = parseFloat(estado.valorUmAtual) + parseFloat(estado.valorDoisAtual)
      return resultadoSoma;
    case 'subtracao':
      const resultadoSubtracao = parseFloat(estado.valorUmAtual) - parseFloat(estado.valorDoisAtual)
      return resultadoSubtracao;
    case 'multiplicacao':
      const resultadoMultiplicacao = parseFloat(estado.valorUmAtual) * parseFloat(estado.valorDoisAtual)
      return resultadoMultiplicacao;
    case 'divisao':
      const resultadoDivisao = parseFloat(estado.valorUmAtual) / parseFloat(estado.valorDoisAtual)
      return resultadoDivisao;
    case 'resto':
      const resultadoResto = parseFloat(estado.valorUmAtual) % parseFloat(estado.valorDoisAtual)
      return resultadoResto;
    default:
      return 'inválido';
  }
}

</script>

<template>
  <div class="container border align-content-center mt-5">
    <h1 class="text-center">Calculadora</h1>
    <div class="row justify-content-around">
      <div class="card col-md-4 text-center border-0">
        <h3 class="card-title">Primeiro número:</h3>
        <input class="rounded-pill card-body text-center" :value="estado.valorUmAtual" @change="evento => estado.valorUmAtual = evento.target.value" type="number" placeholder="0">
      </div>
      <div class="card col-md-1 text-center align-self-center mt-5 border-0">
        <select class="card-title text-center rounded-pill p-2" @change="evento => estado.operacao = evento.target.value">
          <option value="soma">+</option>
          <option value="subtracao">-</option>
          <option value="multiplicacao">x</option>
          <option value="divisao">/</option>
          <option value="resto">%</option>
        </select>
      </div>
      <div class="card col-md-4 text-center border-0">
        <h3 class="card-title">Segundo número:</h3>
        <input class="rounded-pill card-body text-center" :value="estado.valorDoisAtual" @change="evento => estado.valorDoisAtual = evento.target.value" type="number" placeholder="0">
      </div>
    </div>
    <div class="row justify-content-center mt-5">
      <div class="col-md-4 justify-content-center d-flex">
        <div class="card border-0" style="width: 18rem;">
          <h2 class="text-center">Resultado</h2>
          <h3 class="card-body rounded-pill border border-info text-center">{{ resultado() }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
