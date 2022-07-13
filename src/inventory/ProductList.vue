<script setup lang="ts">
const props = defineProps<{
  title: string,
  items: {
    name: string,
    price: number,
    outOfStock?: boolean,
  }[],
}>();
</script>

<template>
  <h2>{{ props.title }}</h2>
  <div v-for="item in props.items" :style="{ color: item.outOfStock ? 'red': 'black' }">
    {{ item.name }} (${{ item.price }})
  </div>
  <div v-if="!props.items.length" style="font-style: italic;">
    No items available.
  </div>
</template>
