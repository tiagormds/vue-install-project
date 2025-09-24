<template>
  <h1>Contador: {{ counter }}</h1>

  <button @click="sumCounter" >Somar</button>
  <button @click="subCounter">Subtrair</button>


  <p>O contado atual está no número: {{ counter }}</p>
</template>

<script>
export default {
  data(){
    return {
      counter: 0,
    }
  },
  methods: {
    sumCounter: function(){
      this.counter += 1;
    },
    subCounter: function(){
      this.counter -= 1;
    },
  }
}
</script>
