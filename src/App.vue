<script setup>
// const name = "Dynamic Vue";
// const styleColor = "color: blue";
// const arrayColor = ["blue", "green", "red"];
// const active = true;
// const arrayFruits = ["apple", "banana", "orange", "grapes", "pear"];
const name = "Dynamic Vue 3";
const arrayFrutas = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una manzana",
    stock: 0,
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una pera",
    stock: 10,
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
    stock: 20,
  },
];
</script>

<template>
  <div>
    <h1>Welcome to {{ name }}</h1>
    <ul>
      <template v-for="item in arrayFrutas" :key="item.name">
        <li v-if="item.stock > 0">{{ item.name }} - {{ item.price }}</li>
      </template>
    </ul>
  </div>
  <!-- 
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="`color: ${arrayColor[1]}`">{{ arrayColor }}</h2>
  <h2 :style="styleColor">I'm blue</h2>
  ========================
  DIRECTIVES
  v-if, v-else, v-else-if conditionals
  <h2 v-if="active">I'm Active</h2>
  <h2 v-if="!active">I'm NOT Active</h2>
  <hr />
  ========================
  OR:
  <h2 v-if="active">I'm actually active, frfr</h2>
  <h2 v-else>I'm not actually active, lol</h2>
  <hr />
  ========================
  OR:
  <h2 v-if="active === true">I'm definitely active</h2>
  <h2 v-else-if="active === false">I'm definitely NOT active, lol</h2>
  <div v-else>
    <h2>I don't know what I am</h2>
    <img src="https://placeimg.com/240/240/any" alt="" />
    <p>I need help, this is not a meme</p>
  </div>
  ========================
  v-show
  <h2 v-show="active">I'm active in spanish</h2>
  ========================
  v-for
  <ul>
    <li v-for="fruit in arrayFruits" :key="fruit">{{ fruit }}</li>
  </ul>
   -->
</template>

<style>
h1 {
  color: red;
}
</style>
