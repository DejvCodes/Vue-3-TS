<template>
  <main>
    <h1>{{ title }}</h1>
    
    <form>
      <label>
        New Task
        <input type="text" v-model="newTask">
      </label>
    </form>
  </main>
</template>

<script setup lang="ts">
  import { ref } from 'vue';

  const title = ref<string>('Tasks App');
  const newTask = ref<string>("");

</script>

<style scoped>
  main {
    max-width: 800px;
    margin: 1rem auto;
    padding: 1rem;
  }
</style>