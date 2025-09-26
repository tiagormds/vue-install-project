<template>
  <h1 ref="templateRef">TemplateRef</h1>
  <p id="welcome" ref="welcome">Hello World</p>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'
console.log('Start na aplicação!')

const welcome = ref(null)

onMounted(() => {
  welcome.value.style.color = 'red'
})
</script>
