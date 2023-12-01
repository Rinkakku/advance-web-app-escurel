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
  .loop-app {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: 'Century Gothic Medium', sans-serif;
    color: #361616;
  }
  
  .loop-title {
    font-size: 36px;
    font-weight: 600;
    margin: 25px 0 20px;
    color: rgb(64, 78, 161);
  }
  
  .loop-item {
    margin: 10px 0;
    padding: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .completed {
    text-decoration: line-through;
    color: #1a1515;
  }
  
  .no-tasks-message {
    text-align: center;
    color: #797474;
    margin-top: 20px;
    font-size: 13px;
  }
  </style>
  
