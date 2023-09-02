<template>
  <div>
    <p v-if="isDisplayed">表示されます</p>
    <p v-else>表示されないはず</p>
    <h2>{{ displayNum }}</h2>
    <p v-if="displayNum > 80">８１以上</p>
    <p v-else-if="displayNum > 50">５１〜８０</p>
    <p v-else-if="displayNum > 20">２１〜５０</p>
    <p v-else>ほげ</p>
  </div>
  <hr />
  <h3>スポーツ一覧</h3>
  <ul>
    <li v-for="item in sports" :key="item">{{ item }}</li>
  </ul>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { ref } from 'vue'

const isDisplayed = ref(true)
const displayNum = computed(() => {
  return Math.round(Math.random() * 100)
})

const sports = ref(['ラグビー', 'volley', 'baseball'])
</script>
