<script setup>
  import { reactive } from 'vue';
  import Formulario from './components/Formulario.vue';

  const estado = reactive({
    NumeroASerConvertido: 0,
    filtro: 'pesoChileno',
  })

const pesoChilenoReal = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido * 0.00597973;
}

const dolarReal = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido * 5.692;
}

const euroReal = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido * 6.1491;
}

const wonReal = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido * 0.00412449 ;
}

const ieneReal = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido * 0.0376637;
}

const realPesoChileno = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido / 0.00597973;
}

const realDolar = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido / 5.692;
}

const realEuro = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido / 6.1491;
}

const realWon = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido / 0.00412449 ;
}

const realIene = ({ NumeroASerConvertido } = estado) => {
  return NumeroASerConvertido / 0.0376637;
}

const resultado = () => {
  const {filtro} = estado;

    switch (filtro) {
      case 'dolarReal':
        return dolarReal();
      case 'euroReal':
        return euroReal();
      case 'wonReal':
        return wonReal();
      case 'ieneReal':
        return ieneReal();
      case 'realPesoChileno':
        return realPesoChileno();
      case 'realDolar':
        return realDolar();
      case 'realEuro':
        return realEuro();
      case 'realWon':
        return realWon();
      case 'realIene':
        return realIene();
      default:
        return pesoChilenoReal();    
    }
  }

</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 text-center">
        <h1>Conversão de moedas:</h1>
    </header>
    <Formulario
      :trocar-filtro="(event) => (estado.filtro = event.target.value)"
      :numero1="(event) => (estado.NumeroASerConvertido = Number(event.target.value))"
    />
    <br>
    <br>
    <h1 class="text-center border border-dark rounded p-5">O resultado é: {{ resultado() }} </h1>
  </div>
  
</template>

<style scoped>
</style>
