<template>
  <div>
    <a :href="linkUrl">{{ linkText }}</a>
    <button :class="buttonClass" @click="onClick">{{ buttonText }}</button>
  </div>
  <div>
    <h1>＃タグ</h1>
    <input type="text" @input="onInput" :value="message" />
    <p>{{ message }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
// リンクのバインド
const linkUrl = ref('https://example.com')
const linkText = ref('Example Link')
const buttonClass = ref('primary')
const buttonText = ref('Click me!')
function onClick() {
  buttonText.value = 'Clicked!'
}

// 文字入力
const message = ref('')
const onInput = (event: Event) => {
  const target = event?.target as HTMLInputElement
  message.value = target.value
}
</script>

<!-- 
  単方向データバインディングと双方向だとどちらがいいのか
  複雑さを回避するためには、単方向バインディングにしたい
  親から子 子から親の値渡しが大変
  デモ単方向よりもスマートに動いてくれる
 -->
