<template>
  <div class="app-container">
    <TheHeader class="header" />

    <!-- 
      Si l'évent "add-product-to-cart" se produit alors on invoque la methode "addProductToCart" 
    -->
    <Shop 
      :products="state.products" 
      @add-product-to-cart="addProductToCart" 
      class="shop" />

    <Cart 
      :cart="state.cart" 
      class="cart" 
      @remove-product-from-cart="removeProductFromCart" />

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


  const state = reactive<{
    products: ProductInterface[],
    cart: ProductInterface[],
  }>({
    products: data,
    cart: []
  })


  function addProductToCart(productId: number): void {
    // On va chercher le produit
    const product = state.products.find(product => product.id === productId);

    // On vérifie si déjà présent dans le cart
    if (product && !state.cart.find(product => product.id === productId)) {
      state.cart.push({...product}); // Déconstruction nécessaire afin de créer un nouveau product ( non lié à celui affiché )
    }
  }

  function removeProductFromCart(productId: number): void {
    // On met à jour le cart avec un filter qui ne garde que les éléméents ne contenant pas l'id du produit
    state.cart = state.cart.filter(product => product.id !== productId) // Déconstruction nécessaire afin de créer un nouveau product ( non lié à celui affiché )
  }


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
