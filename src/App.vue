<script setup lang="ts">
import { computed, ref } from 'vue';
import Header from './header/Header.vue';
import Home from './home/Home.vue';
import Inventory from './inventory/Inventory.vue';

const routes: {
  [x: string]: any
} = {
  '/': Home,
  '/inventory': Inventory,
};

const currentPath = ref(window.location.hash);

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'];
});
</script>

<template>
  <Header />
  <component v-if="currentView" :is="currentView" />
</template>
