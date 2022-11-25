<script setup>
import { ref } from "vue";
const name = "Dynamic Vue 3";
const counter = ref(0);
const increment = () => {
  counter.value++;
};
const decrement = () => {
  counter.value--;
};

const reset = () => {
  counter.value = 0;
};
</script>

<template>
  <main @click.right.prevent>
    <h1>Welcome to {{ name }}</h1>
    <div v-if="counter < 0">
      <h2 :class="'negative'">{{ counter }}</h2>
    </div>
    <div v-else-if="counter > 0">
      <h2 :class="'positive'">{{ counter }}</h2>
    </div>
    <div v-else>
      <h2>{{ counter }}</h2>
    </div>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
    <button @click="reset">Reset</button>
  </main>
</template>

<style lang="scss">
.positive {
  color: green;
}

.negative {
  color: red;
}
</style>
