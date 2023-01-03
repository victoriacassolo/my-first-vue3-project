<script setup>
import { ref, watch } from 'vue';

const count = ref(0);

watch(count, (newCount) => {
  if (newCount < 0) {
    count.value = 0;
  }
});

const sumCount = () => {
  count.value++;
  console.log(count.value);
};

const subCount = () => {
  count.value === 0 ? (count.value = 0) : count.value--;
  console.log(count.value);
};

/* other options to (button --)
<button @click="count === 0 ? (count = 0) : count--">-</button>
 */
</script>

<template>
  <main>
    <div>
      <h4>The current count is...</h4>
      <h1>{{ count }}</h1>
      <button @click="sumCount()">+</button>
      <button @click="subCount()">-</button>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
