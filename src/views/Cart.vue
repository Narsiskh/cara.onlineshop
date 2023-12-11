<script setup lang="ts">
import type {Product} from "@/interfaces"
import {type Ref, ref} from "vue"
import CartProduct from "@/components/CartProduct.vue"


const total = ref(0)
const totalArr: Ref<number[]> = ref([])

const cartProducts: Ref<Product[]> = ref([
  {
    "id": 1,
    "img": "../img/products/f1.jpg",
    "brand": "adidas",
    "name": "Hawaiian Shirt",
    "price": "$139",
    "type": "Home / Shirt",
    "details": "The Hawaiian Shirt is made from a substantial 6.0 oz. per sq. yd. fabric constructed from 100% cotton, this classic fit preshrunk jersey knit provides unmatched comfort with each wear. Featuring a taped neck and shoulder, and a seamless double-needle collar, and available in a range of colors, it offers it all in the ultimate head-turing package."
  },
  {
    "id": 2,
    "img": "../img/products/f2.jpg",
    "brand": "adidas",
    "name": "Hawaiian Shirt",
    "price": "$139",
    "type": "Home / Shirt",
    "details": "The Hawaiian Shirt is made from a substantial 6.0 oz. per sq. yd. fabric constructed from 100% cotton, this classic fit preshrunk jersey knit provides unmatched comfort with each wear. Featuring a taped neck and shoulder, and a seamless double-needle collar, and available in a range of colors, it offers it all in the ultimate head-turing package."
  },
  {
    "id": 3,
    "img": "../img/products/f3.jpg",
    "brand": "adidas",
    "name": "Hawaiian Shirt",
    "price": "$53",
    "type": "Home / Shirt",
    "details": "The Hawaiian Shirt is made from a substantial 6.0 oz. per sq. yd. fabric constructed from 100% cotton, this classic fit preshrunk jersey knit provides unmatched comfort with each wear. Featuring a taped neck and shoulder, and a seamless double-needle collar, and available in a range of colors, it offers it all in the ultimate head-turing package."
  }
].map((value) => {
  total.value += parseInt(value.price.split("$")[1])
  totalArr.value.push(total.value)

  return value
}))

</script>

<template>
  <section id="page-header" class="cart-header d-flex flex-column justify-content-center w-100">
    <h2>#cart</h2>

    <p>Add your coupon code & SAVE upto 70%!</p>
  </section>

  <section id="cart" class="section-p1">
    <table class="w-100">
      <thead>
      <tr>
        <td>Remove</td>
        <td>Image</td>
        <td>Product</td>
        <td>Price</td>
        <td>Quantity</td>
        <td>Subtotal</td>
      </tr>
      </thead>
      <tbody>
      <CartProduct v-for="(product, index) in cartProducts" :key="product.id" :product="product" :total="totalArr[index]"/>
      </tbody>
    </table>
  </section>

  <section id="cart-add" class="section-p1 d-flex flex-wrap justify-content-between">
    <div id="coupon" class="w-50">
      <h3>Apply Coupon</h3>
      <div>
        <input type="text" placeholder="Enter Your Coupon">
        <button class="normal">Apply</button>
      </div>
    </div>

    <div id="subtotal" class="w-50">
      <h3>Cart Totals</h3>
      <table class="w-100">
        <tr>
          <td>Cart Subtotal</td>
          <td>$ 335</td>
        </tr>
        <tr>
          <td>Shipping</td>
          <td>Free</td>
        </tr>
        <tr>
          <td><strong>Total</strong></td>
          <td><strong>$ 335</strong></td>
        </tr>
      </table>
      <button class="normal">Proceed to checkout</button>
    </div>
  </section>
</template>

<style src="../assets/cart.sass" lang="sass"></style>