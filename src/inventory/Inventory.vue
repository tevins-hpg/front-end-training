<script setup lang="ts">
import ProductList from './ProductList.vue';

const sportingGoods = [
  { name: "Football", price: 49.99 },
  { name: "Baseball", price: 9.99 },
  { name: "Basketball", price: 29.99 },
];
const electronics = [
  { name: "Galaxy S22 Ultra", price: 499 },
  { name: "MacBook Pro", price: 1299 },
];
const coffee = [
  { name: "Gevalia", price: 9.99 },
  { name: "Illy", price: 14.99 },
];
</script>

<template>
  <h1>Inventory</h1>
  <ProductList title="Sporting Goods" :items="sportingGoods" />
  <ProductList title="Electronics" :items="electronics" />
  <ProductList title="Coffee" :items="coffee" />
</template>
