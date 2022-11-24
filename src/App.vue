<script setup>
const name = "Dynamic Vue";
const styleColor = "color: blue";
const arrayColor = ["blue", "green", "red"];
const active = true;
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="`color: ${arrayColor[1]}`">{{ arrayColor }}</h2>
  <h2 :style="styleColor">I'm blue</h2>
  <h2>{{ active ? "I'm active" : "I'm not active" }}</h2>
</template>

<style>
h1 {
  color: red;
}
</style>
