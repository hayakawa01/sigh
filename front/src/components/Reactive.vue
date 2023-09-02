<template>
  <div>
    <p>商品価格: {{ price }}円</p>
    <p>消費税込み価格: {{ priceIncludingTax }}円</p>
    <button @click="handleClick">ボタン</button>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
// 通常価格
const price = ref(1000)
// 消費税の計算
const priceIncludingTax = computed(() => {
  const taxRate = 0.1
  return Math.round(price.value * (1 + taxRate))
})
// ボタンクリック（reactiveで）
function handleClick() {
  price.value += 100
  console.log(price.value)
}
</script>
