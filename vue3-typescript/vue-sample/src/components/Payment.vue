<script setup lang="ts">
  const itemName1 = "Desk"
  const itemName2 = "Bike"

  const price1 = 40000
  const price2 = 20000

  const url1 = "https://flexispot.jp/standing-desk/e9.html?gclid=CjwKCAjwjtOTBhAvEiwASG4bCE_eT44g8UjiYePQaQm9kCXldYW8_Mqp87KR2S5ocYsMKZPLjocVFxoCm3EQAvD_BwE"
  const url2 = "https://item.rakuten.co.jp/55cycling/4571487004936/?scid=s_kwa_pla_unpaid_201689"
</script>

<template>
<div class="container">
  <h1>最近の支出</h1>
  <div class="payment">
    <label>{{ itemName1 }}</label>
    <label>{{ price1 }} yen</label>
    <a v-bind:href="url1">bought at...</a>
  </div>
  <div class="payment">
    <label>{{ itemName2 }}</label>
    <label>{{ price2 }} yen</label>
    <a v-bind:href="url2">bought at...</a>
  </div>
</div>
</template>

<style scoped>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .payment {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    width: 400px;
    background-color: aliceblue;
    margin-bottom: 8px;
  }
  label {
    font-size: 20px;
    font-weight: bold;
  }
</style>