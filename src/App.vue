<script setup>
import { ref } from 'vue'

const input = ref('web')
</script>
<template>
    <!-- reactivity-->
    <!--two-way binding-->
    <select v-model="input">
    <option value="web">web</option>
    <option value="net">net</option>
    <option value="others">others</option>
    </select>
    <p>{{ input }}</p>
    <!--conditional-->
    <p v-if="input =='web'"> Web Development</p>
    <p v-else-if="input == 'net'">Networking</p>
    <p v-else>others</p>

    <p v-if="input == 'web'"> Web Development</p> 
    <p v-else>others</p>
    <!--commit, and push-->


    </template>
