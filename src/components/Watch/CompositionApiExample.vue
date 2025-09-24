<template>
  <h1>Watch</h1>

  <label for="">Nome do Usuário:</label>
  <input type="text" v-model="form.name" />

  <label for="">Aceitar termos de uso</label>
  <input type="checkbox" v-model="form.terms" />

  <p>{{ form.terms }}</p>
  <p>{{ status }}</p>
</template>

<script setup lang="ts">
import { reactive, ref, watch } from 'vue'

const form = reactive({
  name: 'Gustavo',
  terms: false
})
const status = ref(null)
const myFunc = () => {
  status.value = 'Pesquisando...'
  setTimeout(() => {
    status.value = 'Aceito!'
  }, 3000)
}

watch(() => form.terms, () => {
  myFunc()
})
</script>
