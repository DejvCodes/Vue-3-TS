<template>
  <button 
    class="secondary" 
    @click="emits('setFilter', props.filter)"
    :class="{
      contrast: props.currentFilter === props.filter
    }"
  >
    {{ props.filter }}
  </button>
</template>

<script setup lang="ts">
  import type { TaskFilter } from '@/types/Types';

  const props = defineProps<{
    filter: TaskFilter;
    currentFilter: TaskFilter;
  }>();

  const emits = defineEmits<{
    setFilter: [filter: TaskFilter];
  }>(); 
</script>

<style scoped>
  button {
    text-transform: capitalize;
  }
</style>