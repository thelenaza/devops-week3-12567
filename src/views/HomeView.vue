<script setup>
import { reactive, ref } from 'vue';
const name = ref()
const state = reactive({age: null})
const ceo = ref('Leena')
const week = ref("Monday")
const countries = ref([
  "Thai","Malaysia","Singapore"
])

</script>

<template>
  <nav>
    <h3>Home Page</h3>
    <div v-for="(country,i) in countries" :key="i">
      {{ i }} - {{ country }}
    </div>
    <hr />
    <span>
      {{ week == 'Monday' ? 'If executed' 
      : week == 'Tueday' ?  'Else If00 executed' 
      : 'Else executed'}}
    </span>
    <hr />
    <span v-if="ceo == 'Sombat'">
      If condition is executed
    </span>

    <span v-else-if="ceo == 'Leena'">
      Else If condition is executed
    </span>

    <!-- <span v-else="ceo == 'Mark'">
      Else condition is executed
    </span> -->

    <p>Hello Name: {{ name }} Age: {{ state.age }}</p>
    Name : <input type="text" v-model="name" > 
    Age : <input type="text" v-model="state.age" >
  </nav>
</template>

<script setup>

</script>

<style scoped>
  nav{
    padding: 10px;
    text-align: center;
  }
</style>