<script setup>
import { ref } from 'vue'

const msg = ref('Compute Product')
const factor1 = ref(0)
const factor2 = ref(0)
const product = ref(0)
const computedClicked = ref(false)

function computeProduct(){
  product.value = factor1.value*factor2.value
  computedClicked.value = true
}

function reset(){
  product.value = 0
  factor1.value = 0
  factor2.value = 0
  computedClicked.value = false
}

</script>

<template>
  <h1>{{ msg }}</h1>
  <img src="https://cdn.theforage.com/vinternships/companyassets/ay2tsYxaTif7Nt6z7/AA4Bnq2tJHALwE8cg/1680718790218/pexels-photo-14197334.jpeg" alt="Plane View"/>
  <br />
  <p>FACTOR 1: {{factor1}}</p>
  <p>FACTOR 2: {{factor2}}</p>
  <input v-model="factor1" /> x <input v-model="factor2" /> =
  
  <br />
  <br />

    <div v-if="!computedClicked">
      <button @click="computeProduct">Compute Product</button>
    </div>
    <div v-else>
      <p>Product: {{product}}</p>
      <button @click="reset">Reset</button>
    </div>
</template>
