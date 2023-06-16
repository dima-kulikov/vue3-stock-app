<script setup>
import { ref } from "vue";
const props = defineProps({
  stock: {
    type: Array,
  },
});
const selectValue = ref("");
console.log(selectValue);
</script>

<template>
  <div class="company-desc">
    <select v-model="selectValue">
      <option value="" disabled>choice of company</option>
      <option v-for="(el, index) in stock" :key="el.symbol" :value="index">
        {{ el.companyName }}
      </option>
    </select>
  </div>
  <div v-if="selectValue !== ''">
    {{ stock[selectValue].description }}
  </div>
</template>