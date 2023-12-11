<script setup lang="ts">
import StarRating from "vue-star-rating"
import type {Product} from "@/interfaces"

defineProps<{
  product: Product
}>()
</script>

<template>
  <div class="pro position-relative">
    <img src="../img/products/f1.jpg" alt="">
    <div class="des">
      <span>{{ product.name }}</span>
      <h5>{{ product.price }}</h5>
      <h4>{{ product.price }}</h4>
    </div>
    <a href="#"><i class="bi bi-cart3 cart"></i></a>
  </div>
</template>

<style src="../assets/ProductCard.sass" scoped lang="sass"></style>