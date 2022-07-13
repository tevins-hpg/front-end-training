<script setup lang="ts">
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
  <h2>Sporting Goods</h2>
  <div v-for="item in sportingGoods">
    {{ item.name }} (${{ item.price }})
  </div>
  <h2>Electronics</h2>
  <div v-for="item in electronics">
    {{ item.name }} (${{ item.price }})
  </div>
  <h2>Coffee</h2>
  <div v-for="item in coffee">
    {{ item.name }} (${{ item.price }})
  </div>
</template>
