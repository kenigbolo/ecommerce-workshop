
<template>
  <div class="bg-white">
    <MainLayout>
      <Products :products="products" :currency="currency"/>
    </MainLayout>
  </div>
</template>

<script setup>
import MainLayout from '~/layouts/MainLayout.vue'
import Products from '~/components/products'
import { useProductsStore } from '~/stores/products'
const productsStore = useProductsStore()
await productsStore.fillProductStore()
await productsStore.getProductCategories()
const { currency, products } = productsStore
</script>