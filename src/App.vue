<template>
  <main>
    <h1>{{ title }}</h1>
    <TaskForm @add-task="addTask" />
  </main>
</template>

<script setup lang="ts">
  import { ref } from 'vue';
  import TaskForm from './components/TaskForm.vue';

  const title = ref<string>('Tasks App');

  const addTask = (newTask: string) => {
    console.log(newTask);
  }
</script>

<style scoped>
  main {
    max-width: 800px;
    margin: 1rem auto;
    padding: 1rem;
  }
</style>