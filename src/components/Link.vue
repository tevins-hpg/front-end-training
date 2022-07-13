<script setup lang="ts">
const props = defineProps<{
  href: string
}>();
</script>

<template>
  <a :href="props.href" class="text-sky-600"><slot></slot></a>
</template>
