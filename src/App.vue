<script setup>
  import { reactive } from 'vue';
  import Header from './components/Header.vue';
  import Form from './components/Form.vue';

const estado = reactive({
  n1: 0,
  n2: 0,
  operacao: 'adicao',
})

const somar = ({ n1, n2 } = estado) => {
  return n1 + n2;
}
const subtrair = ({ n1, n2 } = estado) => {
  return n1 - n2;
}
const multiplicar = ({ n1, n2 } = estado) => {
  return n1 * n2;
}
const dividir = ({ n1, n2 } = estado) => {
  return n1 / n2;
}

const resultado = () => {
  const {n1, n2, operacao} = estado;

  if((n1, n2)) {
    switch (operacao) {
      case 'adicao':
        return somar();
      case 'subtracao':
        return subtrair();
      case 'multiplicacao':
        return multiplicar();
      case 'divisao': 
      return dividir();
    }
  }
}
</script>

<template>
  <div class="container text-center">
    <Header/>
    <Form
    :trocar-filtro="(event) => (estado.operacao = event.target.value)"
    :valor-n1="(event) => (estado.n1 = Number(event.target.value))"
    :valor-n2="(event) => (estado.n2 = Number(event.target.value))"
    />
    <div class="resultado">
        <h2 class="mt-4"> Resultado </h2>
        <p class="display-4">{{ resultado() }}</p>
    </div>
  </div>
</template>


