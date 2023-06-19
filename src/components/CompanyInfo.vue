<script setup>
import { ref } from "vue";
const props = defineProps({
  stock: {
    type: Array,
  },
});
const selectValue = ref("");
</script>

<template>
  <div class="company-desc">
    <h2>Select a company to learn more information about it:</h2>
    <select v-model="selectValue">
      <option value="" disabled>choice of company</option>
      <option v-for="(el, index) in stock" :key="el.symbol" :value="index">
        {{ el.companyName }}
      </option>
    </select>
  </div>
  <div v-if="selectValue !== ''">
    <h3>{{ stock[selectValue].companyName }}</h3>
    {{ stock[selectValue].description }}
  </div>
</template>