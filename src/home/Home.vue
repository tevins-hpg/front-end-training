<script setup lang="ts">
import { ref } from 'vue';
import PageHeader from '../components/PageHeader.vue';
import AppInput from '../components/AppInput.vue';

const inputText = ref('');
</script>

<template>
  <PageHeader>Home</PageHeader>

  <AppInput v-model="inputText" />

  <p>Type something!</p>
  <p v-if="inputText">We're doing some really cool things with "{{ inputText }}".</p>
</template>
