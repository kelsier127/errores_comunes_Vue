<script setup>
import { shuffle } from 'lodash'
import { ref,watch } from 'vue'

let text = ref("")

watch(text, (newValue, oldValue)=>{
  console.log(`\nAntic valor: ${oldValue}` )
  console.log(`Nou valor: ${newValue}` )
})

const items = ref([
  { id: 1, label: 'first name' },
  { id: 2, label: 'last name' },
  { id: 3, label: 'email' },
  { id: 4, label: 'website' }
])

function shuffleItems() {
  items.value = shuffle(items.value)
}
</script>

<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item">{{ item.label }} 
          <input v-model="text" type="text" /></li>
    </ul>
    <button @click="shuffleItems">Shuffle</button>
  </div>

</template>

<style>
ul {
  padding: 0;
  padding-right: 10px;
  margin: 0;
  margin-bottom: 10px;
  list-style: none;
}
input {
  max-width: 100%;
}
</style>