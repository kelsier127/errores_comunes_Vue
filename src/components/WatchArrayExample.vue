<script setup>
import { ref, watch } from 'vue'
const numbers = ref([])

watch(
  numbers, 
  (newValue) => {
    console.log('new number added:'+ numbers.value[numbers.value.length-1])
    console.log(newValue)
  },{
    deep:true
  }
)

const randomNum = () => numbers.value.push((Math.random()*100).toFixed(0))
</script>
<template>
  <button @click="randomNum">Add Random Number</button>
</template>