<!-- ConversionTool.vue -->
<template>
  <div>
    <h2>Conversion Tool</h2>
    <div class="form-group">
      <label>Enter Length:</label>
      <input type="number" v-model="inputValue" class="form-control">
    </div>

    <div class="form-group">
      <label>Conversion Type:</label>
      <select v-model="conversionType" class="form-select">
        <option value="metersToFeet">Meters to Feet</option>
        <option value="feetToMeters">Feet to Meters</option>
      </select>
    </div>

    <div class="result">
      <p>Result: {{ convertedValue }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

const inputValue = ref(0);
const conversionType = ref('metersToFeet');

const convertedValue = computed(() => {
  if (conversionType.value === 'metersToFeet') {
    return inputValue.value * 3.28084; // 1 meter = 3.28084 feet
  } else if (conversionType.value === 'feetToMeters') {
    return inputValue.value / 3.28084; // 1 foot = 0.3048 meters
  }
  return 0;
});
</script>
