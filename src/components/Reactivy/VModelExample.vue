<template>
  <h1>V-model</h1>

  <h2>{{ form.name }}</h2>

  <form @submit.prevent="submitForm">
    <label for="name">Nome</label>
    <input type="text" name="name" id="name" v-model="form.name" />

    <label for="email">E-mail</label>
    <input type="email" name="email" id="email" v-model="form.email" />

    <button type="submit">Enviar</button>
  </form>
</template>

<script setup lang="ts">
import { reactive } from 'vue'

const form = reactive({
  name: 'Gustavo Web',
  email: '',
})

const submitForm = () =>{
  console.log(form.name, form.email)
}
</script>
