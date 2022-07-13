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
  <div class="bg-gray-100 inline-block p-3 mb-2 rounded-md">
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
    <label for="inStockOnly" class="ml-2 text-sm">Show only in stock items</label>
  </div>
</template>
