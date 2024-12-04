<script setup>
import { ref } from 'vue';

const id = '1';
const urlDetailProduct = 'https://67414054e4647499008d305b.mockapi.io/api/v1/products/' + id;
const product = ref({})

async function getProduct() {
  product.value = await (await fetch(urlDetailProduct)).json();
}
getProduct();
</script>

<template>
  <div class="container">
    <h1>{{ product.name }} - {{ product.id }}</h1>
    <p>Quantity: {{ product.quantity }}</p>
    <p>Price: {{ product.price }}</p>
    <p>{{ product.description }}</p>
  </div>
</template>
