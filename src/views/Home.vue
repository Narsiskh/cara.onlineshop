<script setup lang="ts">
import ProductCard from "@/components/ProductCard.vue"
import data from "@/data/data.json"
import {computed} from "vue"
import type {Product} from "@/interfaces";


const products: Product[] = data

const featuredProducts = computed(() => products.slice(0, 8))
const newArrivals = computed(() => products.slice(8, 16))
</script>

<template>
  <section id="hero" class="d-flex flex-column align-items-start justify-content-center w-100">
    <h4 class="pb-15">Trade-in-offer</h4>
    <h2>Super value deals</h2>
    <h1>On all products</h1>
    <p>Save more with coupons & up to 70% off!</p>
    <button class="border-0">Shop Now</button>
  </section>

  <section id="feature" class="section-p1 d-flex align-items-center justify-content-between flex-wrap">
    <div class="fe-box d-inline-block">
      <img class="w-100 mb-10" src="../img/features/f1.png" alt="">
      <h6>Free Shipping</h6>
    </div>
    <div class="fe-box d-inline-block">
      <img src="../img/features/f2.png" alt="">
      <h6>Online Order</h6>
    </div>
    <div class="fe-box d-inline-block">
      <img src="../img/features/f3.png" alt="">
      <h6>Save Money</h6>
    </div>
    <div class="fe-box d-inline-block">
      <img src="../img/features/f4.png" alt="">
      <h6>Promotions</h6>
    </div>
    <div class="fe-box d-inline-block">
      <img src="../img/features/f5.png" alt="">
      <h6>Happy Sell</h6>
    </div>
    <div class="fe-box d-inline-block">
      <img src="../img/features/f6.png" alt="">
      <h6>F24/7 Support</h6>
    </div>
  </section>

  <section class="products section-p1">
    <h2>Featured Products</h2>
    <p>Summer Collection New Design</p>

    <div class="pro-container d-flex justify-content-between flex-wrap pt-20">
        <ProductCard
            v-for="item in featuredProducts"
            :key='item.id' :product="item"
            @click="$router.push(`/products/${item.id}`)"
        />
    </div>
  </section>

  <section id="banner" class="section-m1 d-flex flex-column justify-content-center align-items-center w-100">
    <h4>Repair Services</h4>
    <h2>Up to <span>70% Off</span> - All T-Shirts & Accessories</h2>
    <button class="normal">Explore More</button>
  </section>

  <section class="products section-p1">
    <h2>New Arrivals</h2>
    <p>Summer Collection New Design</p>
    <div class="pro-container d-flex justify-content-between flex-wrap pt-20">
        <ProductCard
            v-for="item in newArrivals"
            :key='item.id' :product="item"
            @click="$router.push(`/products/${item.id}`)"
        />
    </div>
  </section>

  <section id="sm-banner" class="section-p1 d-flex flex-wrap justify-content-between">
    <div class="banner-box d-flex flex-column justify-content-center align-items-start">
      <h4>crazy deals</h4>
      <h2>buy 1 get 1 free</h2>
      <span>The best classic dress is on sale at cara</span>
      <button class="white">Learn More</button>
    </div>

    <div class="banner-box banner-box2 d-flex flex-column justify-content-center align-items-start">
      <h4>spring/summer</h4>
      <h2>upcomming seasons</h2>
      <span>The best classic dress is on sale at cara</span>
      <button class="white">Learn More</button>
    </div>
  </section>

  <section id="banner3" class="d-flex justify-content-between flex-wrap">
    <div class="banner-box d-flex flex-column justify-content-center align-items-start mb-20 p-20">
      <h2>SEASONAL SALE</h2>
      <h3>Winter Collection -50% OFF</h3>
    </div>
    <div class="banner-box banner-box2 d-flex flex-column justify-content-center align-items-start mb-20 p-20">
      <h2>NEW FOOTWEAR COLLECTION</h2>
      <h3>Spring/Summer 2023</h3>
    </div>
    <div class="banner-box banner-box3 d-flex flex-column justify-content-center align-items-start mb-20 p-20">
      <h2>T-SHIRTS</h2>
      <h3>New Trendy Prints</h3>
    </div>
  </section>
</template>

<style src="../assets/home.sass" scoped lang="sass"></style>