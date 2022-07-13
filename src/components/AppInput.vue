<script setup lang="ts">
const props = defineProps<{
  modelValue: string
}>();

defineEmits<{
  (e: 'update:modelValue', value: string): void
}>();
</script>

<template>
  <!-- https://vuejs.org/guide/components/events.html#usage-with-v-model -->
  <input
    :value="props.modelValue"
    @input="$emit('update:modelValue', $event.target?.value)"
    class="p-1 border rounded-md block"
    placeholder="Search..."
  />
</template>
