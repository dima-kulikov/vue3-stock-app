<script setup>
import axios from "axios";
import Stocks from "./components/Stocks.vue";
const name = "Dima its worck";

const stock = [];
const errors = [];
// https://www.youtube.com/watch?v=7Qgoki16SRs&t=1266s    17-00
axios
  .get(
    "https://financialmodelingprep.com/api/v3/profile/AAPL,NVDA,TSLA,AMD,INTC,MDB,SPCE,V,DAL,DOCU,OKTA,AMZN,PINS,TRIP,GDDY,DIS,MCD,NOK,UPWK,IBM,FB,ZM,OZON,NFLX,EA,HLT,H,CCL?apikey=03c40d82e1c83ce471a2db45a70eee0f"
  )
  .then((res) => {
    stock.value = res.data;
    console.log(stock);
  })
  .catch((e) => {
    errors.value.push(e);
  });
</script>

<template>
  <h1>HELLO</h1>
  <Stocks :name="name" />
</template>

<style scoped>
</style>
