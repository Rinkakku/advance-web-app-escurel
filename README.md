# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Activity 3 
<template>
    <div class="todo-app">
      <h1 class="todo-title">My To-Do List</h1>
      <div class="todo-form">
        <input
          type="text"
          v-model="newTask"
          @keyup.enter="addTask"
          placeholder="Add a new task"
          class="task-input"
        />
        <button @click="addTask" class="add-button">Add</button>
      </div>
      <div class="todo-list">
        <div v-if="tasks.length === 0" class="no-tasks-message">
          <p>No tasks to do!</p>
        </div>
        <div v-for="(task, index) in tasks" :key="index" class="task-item">
          <label class="task-label">
            <input
              type="checkbox"
              v-model="task.completed"
              class="task-checkbox"
            />
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
        tasks: [],
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
  .todo-app {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    height: 100vh;
    background-color: #fff;
    font-family: 'Century Gothic Medium';
    font-weight: 400;
    color: #361616;
    overflow-y: auto;
  }
  
  .todo-title {
    font-size: 36px;
    font-weight: 600;
    margin-top: 25px;
    margin-bottom: 20px;
    color: rgb(64, 78, 161);
  }
  
  .todo-form {
    display: flex;
    align-items: center;
    background-color: #f3eded27;
    border-radius: 7px;
    padding: 10px;
    box-shadow: 0 2px 4px rgba(22, 20, 20, 0.1);
    width: 100%;
    max-width: 400px;
    margin-bottom: 2px;
  }
  
  .task-input {
    flex-grow: 1;
    padding: 10px;
    border: none;
    border-radius: 5px;
    font-size: 15px;
    outline: none;
    color: #6d6e6b;
  }
  
  .add-button {
    padding: 10px 21px;
    background-color: #699bd1;
    font-weight: 530;
    color: #ffffff;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }
  
  .add-button:hover {
    background-color: #1975e6;
  }
  
  .todo-list {
    width: 100%;
    max-width: 400px;
  }
  
  .task-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 10px 0;
    background-color: #fff;
    border-radius: 5px;
    padding: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
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
    color: #1a1515;
  }
  
  .remove-button {
    padding: 5px 10px;
    background-color: #ee0909;
    color: #fff;
    border: none;
    border-radius: 5px;
    font-size: 14px;
    font-weight: 550;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;
  }
  
  .remove-button:hover {
    background-color: #463737;
  }
  
  .no-tasks-message {
    text-align: center;
    color: #797474;
    margin-top: 20px;
    font-size: 13px;
  }
  </style>
  