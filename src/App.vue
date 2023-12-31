<!-- App.vue -->
<template>
  <div class="container py-5" style="height: 100vh;">
    <div class="row">
      <div class="col-md-3">
        <!-- Micro Tool Buttons -->
        <button class="micro-tool-button" @click="showTool('flexbox')">Flexbox Tool</button>
        <button class="micro-tool-button" @click="showTool('conversion')">Conversion Tool</button>
        <button class="micro-tool-button" @click="showTool('calculator')">Calculator Tool</button>
      </div>

      <div class="col-md-9">
        <!-- Micro Tool Components -->
        <flexbox-tool v-if="activeTool === 'flexbox'"></flexbox-tool>
        <conversion-tool v-if="activeTool === 'conversion'"></conversion-tool>
        <calculator-tool v-if="activeTool === 'calculator'"></calculator-tool>
      
      </div>
    </div>
  </div>
</template>

<style>
.micro-tool-button {
  display: block;
  width: 200px; 
  height: 100px; 
  padding: 30px; 
  margin-bottom: 100px; 
  background-color: rgb(139, 35, 35);
  color: white;
  font-weight: bold;
  border: none;
  border-radius: 8px; 
  cursor: pointer;
  transition: background-color 0.3s;
  /* Adjust the features or chars as needed */
}

.micro-tool-button:hover {
  background-color: rgb(139, 35, 35);
}
</style>

<script>
import { ref } from 'vue';
import FlexboxTool from './FlexboxTool.vue';
import ConversionTool from './ConversionTool.vue';
import CalculatorTool from './CalculatorTool.vue';

export default {
  data() {
    return {
      activeTool: 'flexbox',
    };
  },
  components: {
    'flexbox-tool': FlexboxTool,
    'conversion-tool': ConversionTool,
    'calculator-tool': CalculatorTool,
    
  },
  methods: {
    showTool(tool) {
      this.activeTool = tool;
    },
  },
};
</script>
