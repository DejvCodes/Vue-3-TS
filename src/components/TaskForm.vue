<template>
  <form @submit.prevent="formSubmit">
    <label>
      New Task
      <input type="text" v-model="newTask">
    </label>
    <div class="button-container">
      <button>Add</button>
    </div>
  </form>
</template>

<script setup lang="ts">
  import { ref } from 'vue';

  const emit = defineEmits<{
    addTask: [newTask: string]
  }>();

  const newTask = ref<string>("");

  const formSubmit = () => {
    if (newTask.value.trim()) {
      emit("addTask", newTask.value);
      newTask.value = '';
    }

  }
</script>

<style scoped>
  .button-container {
    display: flex;
    justify-content: flex-end;
  }
</style>