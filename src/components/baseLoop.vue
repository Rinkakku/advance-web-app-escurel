<template>
    <div class="loop-app">
      <h1 class="loop-title">Looping To-Do List</h1>
      <div v-if="tasks.length === 0" class="no-tasks-message">
        <p>No tasks to loop through!</p>
      </div>
      <div v-for="(task, index) in tasks" :key="index" class="loop-item">
        <span :class="{ completed: task.completed }">{{ task.text }}</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      tasks: Array,
    },
  };
  </script>
  
  <style scoped>
  /* Your styles for BaseLoop.vue */
  </style>
  