<template>
  <TransitionGroup name="my-list" tag="div" class="task-list">
    <article v-for="task in props.tasks" :key="task.id" class="task">
      <label>
        <input 
          @input="emits('toggleDone', task.id)" 
          :checked="task.done" 
          type="checkbox"
        >
        <span :class="{done: task.done}">{{ task.title }}</span>
      </label>
      <button 
        @click="emits('removeTask', task.id)" 
        class="outline"
      >
        Remove
      </button>
    </article>
  </TransitionGroup>
</template>

<script setup lang="ts">
  import type {Task} from '@/types/Types';

  const props = defineProps<{
    tasks: Task[];
  }>();

  const emits = defineEmits<{
    toggleDone: [id: string];
    removeTask: [id: string];
  }>();
</script>

<style scoped>
  .task-list {
    margin-top: 1rem;
  }
  .done {
    text-decoration: line-through;
  }
  .task {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .my-list-enter-active,
  .my-list-leave-active {
    transition: all 0.5s ease;
  }
  .my-list-enter-from,
  .my-list-leave-to {
    opacity: 0;
    transform: translateX(30px);
  }
</style>