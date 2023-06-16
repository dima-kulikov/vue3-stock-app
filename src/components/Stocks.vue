<script setup>
const props = defineProps({
  item: {
    type: [Object, null],
  },
});
function priceNumber(price) {
  if (price == null) {
    return 0;
  } else {
    return price;
  }
}
</script>

<template>
  <div class="item-block-item">
    <img :src="item.image" :alt="item.companyName" />
    <div class="item-block-item__name">
      <div class="item-block-item__name-companyname">
        {{ item.companyName }}
      </div>
      <div class="item-block-item__name-symbol">{{ item.symbol }}</div>
    </div>
    <div class="item-block-item__price">
      {{ priceNumber(item.price) }}
      $
    </div>
  </div>
</template>


