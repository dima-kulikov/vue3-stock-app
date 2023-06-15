<script setup>
const props = defineProps({
  name: {
    type: String,
  },
});
</script>

<template>
  <h2>{{ name }}</h2>
</template>

<style scoped>
</style>
