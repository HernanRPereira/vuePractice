<script setup>
import { ref, computed } from 'vue'
const name = "Vue dinamico";
// const styleColor = "color:blue";
// const listaColor = ["red", "green", "black", "yellow"];
// const arrayColores = listaColor
// const colorName = listaColor
// const activo = null;
// const arrayFrutas = ["🍎", "🍉", "🍒", "🍍", "🍐", "🍇"];
// const isColorLista = true;

// const arrayFrutas = [
//   {
//     name: "Manzana",
//     price: "$1.00",
//     description: "Una manzana",
//   },
//   {
//     name: "Pera",
//     price: "$2.00",
//     description: "Una pera",
//   },
//   {
//     name: "Naranja",
//     price: "$3.00",
//     description: "Una naranja",
//   },
// ];
const counter = ref(0);

const increment = () => {
  counter.value += 1;
};

const reset = () => {
  counter.value = 0;
};

const decrease = () => {
  counter.value -= 1;
};

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "cero";
  }
  if (counter.value > 0) {
    return "positive";
  }
  if (counter.value < 0) {
    return "negative";
  }
})
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <!-- <h2>{{ arrayColores }}</h2>
  <h2 :style="`color: ${arrayColores[1]}`">Soy {{ colorName[1] }}</h2>
  <h2 v-if="activo === true">Estoy activado</h2>
  <p v-else-if="activo === false">Estoy Desactivado</p>
  <p v-else>Indeciso</p> -->
  <!-- <ul>
    <li 
    v-for="(fruta, index) in arrayFrutas"
    :key="index"
    >
      {{ index }} - {{ fruta }}
    </li>
  </ul> -->
  <!-- <ul v-bind:class="{ colorLista: isColorLista}">
    <li v-for="fruta in arrayFrutas" :key="fruta.name">
      {{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}
    </li>
  </ul> -->

  <h2 v-bind:class="classCounter">{{ counter }}</h2>

  <button v-on:click="increment">Aumentar</button>
  <button @:click="reset">Resetear</button>
  <button v-on:click="decrease">Disminuir</button>

</template>

<style>
h1 {
  color: red;
}

.colorLista {
  color: blue;
  background-color: yellow;
  padding: 10px;
  border-radius: 10px;
  margin: 10px;
  box-shadow: 10px 10px 10px black;
  text-align: center;
  font-size: 20px;
}

.negative {
  color: red;
}

.positive {
  color: green;
}

.cero{
  color: purple
}
</style>