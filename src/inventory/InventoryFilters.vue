<script setup lang="ts">
const props = defineProps<{
  searchText: string;
  inStockOnly: boolean;
}>();

defineEmits<{
  (e: 'update:searchText', value: string): void
  (e: 'update:inStockOnly', value: boolean): void
}>();
</script>

<template>
  <!-- https://vuejs.org/guide/components/events.html#usage-with-v-model -->
  <input
    :value="props.searchText"
    @input="$emit('update:searchText', $event.target?.value)"
    style="padding: 0.5rem; border-color:lavender; display: block;"
    placeholder="Search..."
  />
  <input
    type="checkbox"
    id="inStockOnly"
    :value="props.inStockOnly"
    @input="$emit('update:inStockOnly', $event.target?.checked)"
  />
  <label for="inStockOnly">Show only in stock items</label>
</template>
