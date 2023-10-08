<template>
    <div>
      <h1 class="app-title">To-Do List</h1>
      <div class="todo-form">
        <input type="text" v-model="newTask" @keyup.enter="addTask" placeholder="Add a new task" class="task-input">
        <button @click="addTask" class="add-button">Add</button>
      </div>
      <div class="todo-list">
        <div v-if="tasks.length === 0" class="no-tasks-message">
          <p>No tasks to do! 🎉</p>
        </div>
        <div v-for="(task, index) in tasks" :key="index" class="task-item">
          <label class="task-label">
            <input type="checkbox" v-model="task.completed" class="task-checkbox">
            <span :class="{ completed: task.completed }" class="task-text">{{ task.text }}</span>
          </label>
          <button @click="removeTask(index)" class="remove-button">Remove</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTask: '',
        tasks: [], // Array of tasks with text and completion status
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim() !== '') {
          this.tasks.push({ text: this.newTask, completed: false });
          this.newTask = '';
        }
      },
      removeTask(index) {
        this.tasks.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Styling for the app title */
  .app-title {
    text-align: center;
    font-size: 24px;
    color: #333;
    margin-bottom: 20px;
  }
  
  /* Styling for the input and button */
  .todo-form {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .task-input {
    padding: 10px;
    width: 60%;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
  }
  
  .add-button {
    padding: 10px 20px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }
  
  .add-button:hover {
    background-color: #0056b3;
  }
  
  /* Styling for the to-do list */
  .todo-list {
    display: flex;
    flex-direction: column;
  }
  
  .task-item {
    display: flex;
    align-items: center;
    margin: 10px 0;
  }
  
  /* Styling for the task checkbox and text */
  .task-label {
    display: flex;
    align-items: center;
  }
  
  .task-checkbox {
    margin-right: 10px;
    cursor: pointer;
  }
  
  .completed {
    text-decoration: line-through;
    color: #888;
  }
  
  /* Styling for the remove button */
  .remove-button {
    padding: 5px 10px;
    background-color: #FF4D4D;
    color: #fff;
    border: none;
    border-radius: 5px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }
  
  .remove-button:hover {
    background-color: #FF0000;
  }
  
  /* Styling for the no tasks message */
  .no-tasks-message {
    text-align: center;
    color: #888;
    margin-top: 20px;
  }
  </style>
  
  