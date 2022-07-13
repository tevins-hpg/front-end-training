<script setup lang="ts">
import AppInput from '../components/AppInput.vue';

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
  <AppInput
    :model-value="props.searchText"
    @update:model-value="$emit('update:searchText', $event)"
  />
  <input
    type="checkbox"
    id="inStockOnly"
    :value="props.inStockOnly"
    @input="$emit('update:inStockOnly', $event.target?.checked)"
  />
  <label for="inStockOnly">Show only in stock items</label>
</template>
