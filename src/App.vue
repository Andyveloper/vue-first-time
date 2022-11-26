<script setup>
import { ref, computed } from "vue";
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

const classCounter = computed(() => {
  if (counter.value < 0) {
    return "negative";
  } else if (counter.value > 0) {
    return "positive";
  } else {
    return "zero";
  }
});
</script>

<template>
  <main @click.right.prevent>
    <h1>Welcome to {{ name }}</h1>
    <div>
      <h2 :class="classCounter">{{ counter }}</h2>
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

.zero {
  color: peru;
}
</style>
