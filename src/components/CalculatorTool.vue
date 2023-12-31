<!-- CalculatorTool.vue -->
<template>
  <div>
    <h2>Calculator Tool</h2>

    <div class="form-group">
      <label>Enter Number 1:</label>
      <input type="number" v-model="number1" class="form-control">
    </div>

    <div class="form-group">
      <label>Enter Number 2:</label>
      <input type="number" v-model="number2" class="form-control">
    </div>

    <div class="form-group">
      <label>Select Operation:</label>
      <select v-model="operation" class="form-select">
        <option value="add">Addition (+)</option>
        <option value="subtract">Subtraction (-)</option>
        <option value="multiply">Multiplication (*)</option>
        <option value="divide">Division (/)</option>
      </select>
    </div>

    <div class="result">
      <p>Result: {{ calculateResult }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const number1 = ref(0);
const number2 = ref(0);
const operation = ref('add'); // Default operation is addition

const calculateResult = computed(() => {
  switch (operation.value) {
    case 'add':
      return number1.value + number2.value;
    case 'subtract':
      return number1.value - number2.value;
    case 'multiply':
      return number1.value * number2.value;
    case 'divide':
      return number1.value / number2.value;
    default:
      return 0;
  }
});
</script>
