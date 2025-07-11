<template>
  <main>
    <h1>{{ title }}</h1>
    <TaskForm @add-task="addTask" />
    <h3>There are {{ tasks.length }} tasks.</h3>
    <article v-for="task in tasks" :key="task.id">
      {{ task.title }}
    </article>
  </main>
</template>

<script setup lang="ts">
  import { ref } from 'vue'; 
  import TaskForm from './components/TaskForm.vue';
  import type { Task } from './types/Types';

  const title = ref<string>('Tasks App');
  const tasks = ref<Task[]>([]);

  const addTask = (newTask: string) => {
    tasks.value.push({
      id: crypto.randomUUID(),
      title: newTask,
      done: false
    })
  }
</script>

<style scoped>
  main {
    max-width: 800px;
    margin: 1rem auto;
    padding: 1rem;
  }
</style>