<script setup lang="ts">
import type {Product} from "@/interfaces"

defineProps<{
  product: Product,
  total: number
}>()
</script>

<template>
  <tr>
    <td><a href="#"><i class="bi bi-x-circle"></i></a></td>
    <td><img src="../img/products/f2.jpg"></td>
    <td>{{ product.name }}</td>
    <td>{{ product.price }}</td>
    <td><input type="number" value="1"></td>
    <td>${{ total }}</td>
  </tr>
</template>

<style scoped lang="sass">

</style>