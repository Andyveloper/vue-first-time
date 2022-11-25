<script setup>
const name = "Dynamic Vue 3";

// methods
const handleClick = (message) => {
  console.log(message);
};
</script>

<template>
  <main @click.right.prevent>
    <h1>Welcome to {{ name }}</h1>
    <button @click.right.prevent="handleClick('text right')">
      Push me right
    </button>
    <button @click.middle="handleClick('text middle')">Push me middle</button>
    <button @click="handleClick('text left')">Push me left</button>
  </main>
</template>
