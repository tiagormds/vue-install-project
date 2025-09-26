<template>
  <h1>Bindings</h1>

  <input :type="input.type" :name="input.name" :placeholder="input.placeholder" />
  <button @click="showHidePassword">Mostrar/Ocultar Senha</button>
</template>

<script setup lang="ts">

import { reactive } from 'vue'

const input = reactive({
  name: 'nameUser',
  type: 'password',
  placeholder: 'Digite seu nome aqui!'
})

const showHidePassword = () => {
  if (input.type === 'text'){
    input.type = 'password'
  }else{
    input.type = 'text'
  }
}
</script>
