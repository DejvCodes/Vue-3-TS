<template>
  <form @submit.prevent="formSubmit">
    <label>
      New Task
      <input
        v-model="newTask" 
        name="newTask"
        :arial-invalid="!!error || undefined"
        @input="error = ''"
      >
      <small v-if="error" id="invalid-helper">
        {{ error }}
      </small>
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
  const error = ref<string>("");

  const formSubmit = () => {
    if (newTask.value.trim()) {
      emit("addTask", newTask.value);
      newTask.value = '';
    } else {
      error.value = 'Task cannot be empty!';
    }
  }
</script>

<style scoped>
  .button-container {
    display: flex;
    justify-content: flex-end;
  }
</style>