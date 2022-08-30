<template>
  <div class="app-container">
    <TheHeader class="header" />
    <Shop :products="products" class="shop" />
    <Cart class="cart" />
    <TheFooter class="footer" />
  </div>
</template>


<script setup lang="ts">
  import TheHeader from './components/Header.vue'
  import Shop from './components/Shop/Shop.vue'
  import Cart from './components/Cart/Cart.vue'
  import TheFooter from './components/Footer.vue'
  
  import data from './data/products'
  import type { ProductInterface } from './interfaces/productinterface'
  import { reactive } from 'vue'

  const products = reactive<ProductInterface[]>(data);
</script>


<style lang="scss">
  @import"./assets/style.scss";

  .app-container {
    min-height: 100vh;
    display: grid;
    grid-template-areas: "header header" "shop cart" "footer footer";
    grid-template-columns: 70% 30%;
    grid-template-rows: 3.5rem auto 3.5rem;
  }

  .header {
    grid-area: header;
  }

  .shop {
    grid-area: shop;
  }

  .cart {
    grid-area: cart;
  }

  .footer {
    grid-area: footer;
  }

</style>
