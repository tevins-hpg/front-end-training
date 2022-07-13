<script setup lang="ts">
import { ref } from 'vue';
import PageHeader from '../components/PageHeader.vue';

const inputText = ref('');
</script>

<template>
  <PageHeader>Home</PageHeader>

  <input v-model="inputText" style="padding: 0.5rem; border-color:lavender; display: block;" placeholder="Search..." />

  <p>Type something!</p>
  <p v-if="inputText">We're doing some really cool things with "{{ inputText }}".</p>
</template>
