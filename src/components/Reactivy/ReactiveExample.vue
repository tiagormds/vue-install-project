<template>
  <h1>Reactive example</h1>
  <p>contador: {{ form.counter }}</p>

  <button @click="sumCounter" >Somar</button>
  <button @click="subCounter">Subtrair</button>
</template>
<script setup lang="ts">

import { reactive } from 'vue'

const form = reactive({
  counter: 0,
})

const sumCounter = function (){
  form.counter += 1;
};

const subCounter = () => {
  form.counter -= 1;
};
</script>
