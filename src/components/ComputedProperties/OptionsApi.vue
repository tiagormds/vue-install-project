<template>
  <h1>ComputedProperties (OptionsAPI)</h1>

  input: <input type="text" v-model="userFullNameWritable" />

  <p>O nome do usuário é: {{ user.first_name }} {{ user.last_name }}</p>
  <p>O nome do usuário é: {{ userFullName }}</p>
</template>

<script>
export default {
  data(){
    return {
      user: {
        first_name: 'Gustavo',
        last_name: 'Web',
      },
      order: {
        price: 99700
      },
    }
  },
  computed:{
    userFullName(){
      return this.user.first_name + ' ' + this.user.last_name
    },
    userFullNameWritable: {
      get(){
        return this.user.first_name + ' ' + this.user.last_name
      },
      set(newValue){
        this.user.first_name = newValue.split(' ')[0]
        this.user.last_name = newValue.split(' ')[1]
      }
    }
  }
}
</script>
