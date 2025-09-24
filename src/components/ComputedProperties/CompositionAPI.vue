<template>
  <h1>Composition API</h1>

  input: <input type="text" v-model="userFullName" />

  <p>O nome completo do usuário é: {{ user.first_name }} {{ user.last_name }}</p>
  <p>O nome completo do usuário é: {{ userFullName }}</p>


  <p>O valor do pedido é: {{ order.price }}</p>
  <p>O valor do pedido é: {{ orderPriceFormated }}</p>
</template>

<script setup>
import { computed, reactive } from 'vue'

const user = reactive({
  first_name: 'Gustavo',
  last_name: 'Web',
})

// const userFullName = computed( () => {
//   return user.first_name + ' ' + user.last_name
// })

const userFullName = computed({
  get(){
    return user.first_name + ' ' + user.last_name
},
set(newValue) {
    user.first_name = newValue.split(' ')[0]
    user.last_name = newValue.split(' ')[1]
}
})

const order = reactive({
  price: 99700
})

const formatCurrency = new Intl.NumberFormat('pt-BR', {
  style: 'currency',
  currency: 'BRL',
  minimumFractionDigits: 2,
})

const orderPriceFormated = computed( () => {
  return formatCurrency.format(order.price / 100)
})
</script>
