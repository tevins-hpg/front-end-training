<script setup lang="ts">
const props = defineProps<{
  title: string,
  items: {
    name: string,
    price: number,
  }[]
}>();
</script>

<template>
  <h2>{{ props.title }}</h2>
  <div v-for="item in props.items">
    {{ item.name }} (${{ item.price }})
  </div>
</template>
