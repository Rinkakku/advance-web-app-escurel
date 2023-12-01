<template>
  <div id="app">
    <BaseCondition></BaseCondition>
    <BaseLoop :tasks="tasks"></BaseLoop>
  </div>
</template>

<script setup>
import BaseCondition from './components/BaseCondition.vue';
import BaseLoop from './components/BaseLoop.vue';
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  font-family: 'century Gothic Medium', sans-serif;
  color: #361616;
  background-color: #f0f0f0;
}

/* Add any global styles you need here */
</style>
