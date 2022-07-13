<script setup lang="ts">
import { computed, ref } from 'vue';
import InventoryFilters from './InventoryFilters.vue';
import ProductList from './ProductList.vue';

const inputText = ref('');
const inStockOnly = ref(false);

const testItem = (item: { name: string, outOfStock?: boolean }) => {
  const search = inputText.value;
  const matchesSearch = !search || item.name.toLowerCase().includes(inputText.value);

  const inStockOnlyVal = inStockOnly.value;
  const matchesStock = !inStockOnlyVal || !item.outOfStock;

  return matchesSearch && matchesStock;
};

const sportingGoods = computed(() => [
  { name: "Football", price: 49.99, outOfStock: true },
  { name: "Baseball", price: 9.99 },
  { name: "Basketball", price: 29.99, outOfStock: true },
].filter(testItem));

const electronics = computed(() => [
  { name: "Galaxy S22 Ultra", price: 499 },
  { name: "MacBook Pro", price: 1299, outOfStock: true },
].filter(testItem));

const coffee = computed(() => [
  { name: "Gevalia", price: 9.99 },
  { name: "Illy", price: 14.99 },
].filter(testItem));
</script>

<template>
  <h1 class="page-header">Inventory</h1>

  <InventoryFilters
    v-model:search-text="inputText"
    v-model:in-stock-only="inStockOnly"
  />

  <ProductList title="Sporting Goods" :items="sportingGoods" />
  <ProductList title="Electronics" :items="electronics" />
  <ProductList title="Coffee" :items="coffee" />
</template>

<style>
.page-header {
  text-transform: uppercase;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
