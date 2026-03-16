<script setup>
import { ref } from 'vue'
import socksGreenImage from '/Users/alphapod/Desktop/Learning_Projects/VueJS/Intro-to-Vue-3-Composition-API/src/assets/images/socks_green.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)
const inStock = true
const details = ref(['50% cotton', '30% wool', '20% polyester'])
const sizes = ref(['S', 'M', 'L', 'XL'])
const soldout = ref(['M','S','L'])
</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">    
        <img v-bind:src="image">
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <ul>
          <li v-for="size in sizes" :key="size">
            <p v-if="size">{{ size }} </p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>