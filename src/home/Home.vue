<script setup lang="ts">
import { ref } from 'vue';

const inputText = ref('');
</script>

<template>
  <h1 class="page-header">Home</h1>

  <input v-model="inputText" style="padding: 0.5rem; border-color:lavender; display: block;" placeholder="Search..." />

  <p>Type something!</p>
  <p v-if="inputText">We're doing some really cool things with "{{ inputText }}".</p>
</template>

<style>
.page-header {
  text-transform: uppercase;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
