<template>
  <h1>Ref example</h1>
  <p>contador: {{ counter }}</p>

  <button @click="sumCounter" >Somar</button>
  <button @click="subCounter">Subtrair</button>
</template>
<script setup lang="ts">
import { ref } from 'vue'

const counter = ref<number>(0)

const sumCounter = function (){
  counter.value += 1;
};

const subCounter = () => {
  counter.value -= 1;
};
</script>
