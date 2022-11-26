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

const favoriteNumbers = ref([]);
const addNumber = () => {
  favoriteNumbers.value.push(counter.value);
  favoriteNumbers.value.sort((a, b) => {
    return a - b;
  });
};
const disableBtn = computed(() => {
  if (favoriteNumbers.value.includes(counter.value)) {
    return true;
  } else {
    return false;
  }
});
</script>

<template>
  <main class="container text-center mt-3" @click.right.prevent>
    <h1>Welcome to {{ name }}</h1>
    <div>
      <h2 :class="classCounter">{{ counter }}</h2>
    </div>
    <div class="btn-group">
      <button class="btn btn-success" @click="increment">Increment</button>
      <button class="btn btn-danger" @click="decrement">Decrement</button>
      <button class="btn btn-secondary" @click="reset">Reset</button>
      <button class="btn btn-primary" @click="addNumber" :disabled="disableBtn">
        Add number
      </button>
    </div>
    <div>
      <h2 class="mt-4">Favorite Numbers List</h2>
      <ul class="list-group mt-2">
        <li
          class="list-group-item"
          v-for="numbers in favoriteNumbers"
          :key="numbers"
        >
          {{ numbers }}
        </li>
      </ul>
    </div>
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
