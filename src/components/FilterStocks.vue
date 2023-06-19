<script setup>
const props = defineProps({
  stock: {
    type: [Array, null],
  },
});
function upPrice(array) {
  array.sort((a, b) => {
    return b.price - a.price;
  });
}
function downPrice(array) {
  array.sort((a, b) => {
    return a.price - b.price;
  });
}
function companyNameUp(array) {
  array.sort((a, b) => {
    return a.companyName.localeCompare(b.companyName);
  });
}
</script>

<template>
  <div class="filter-block">
    <button @click="upPrice(stock)">Price UP</button>
    <button @click="downPrice(stock)">Price Down</button>
    <button @click="companyNameUp(stock)">Company Name</button>
    <!-- <ul>
      <li v-for="el in stock" :key="el.symbol">{{ el.companyName }}</li>
    </ul> -->
  </div>
</template>