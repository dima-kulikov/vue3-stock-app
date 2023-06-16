<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

import Stocks from "./components/Stocks.vue";
import CompanyInfo from "./components/CompanyInfo.vue";

const stock = ref(null);
const errors = [];
// https://www.youtube.com/watch?v=7Qgoki16SRs&t=1266s    17-00

function AxiosArr() {
  axios
    .get(
      "https://financialmodelingprep.com/api/v3/profile/AAPL,NVDA,TSLA,AMD,INTC,MDB,SPCE,V,DAL,DOCU,OKTA,AMZN,PINS,TRIP,GDDY,DIS,MCD,NOK,UPWK,IBM,FB,ZM,OZON,NFLX,EA,HLT,H,CCL?apikey=03c40d82e1c83ce471a2db45a70eee0f"
    )
    .then((res) => {
      stock.value = res.data;
    })
    .catch((e) => {
      errors.value.push(e);
    });
}
onMounted(AxiosArr);
</script>

<template>
  <div class="block">
    <div class="block-flex">
      <h1>Shop price list</h1>
      <div class="items-block">
        <Stocks v-for="item in stock" :key="item.symbol" :item="item" />
      </div>
    </div>
    <CompanyInfo :stock="stock" />
  </div>
</template>


