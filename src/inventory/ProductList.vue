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
  <div class="mb-2">
    <h2 class="font-bold text-xl">{{ props.title }}</h2>
    <div
      v-for="item in props.items"
      :class="{ 'text-red-500': item.outOfStock }"
    >
      {{ item.name }} (${{ item.price }})
    </div>
    <div v-if="!props.items.length" class="italic">
      No items available.
    </div>
  </div>
</template>
