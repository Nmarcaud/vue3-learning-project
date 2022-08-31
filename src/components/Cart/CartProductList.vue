<template>
    <div class="d-flex flex-column">
        <CartProduct v-for="product in cart" :product="product" :key="product.id" @remove-product-from-cart="emit('removeProductFromCart', $event)"/>
    </div>
</template>


<script setup lang="ts">
    import CartProduct from "./CartProduct.vue";
    import type { ProductCartInterface } from "@/interfaces";
    
    defineProps<{
        cart: ProductCartInterface[]
    }>()

    const emit = defineEmits<{
        (e: 'removeProductFromCart', productId: number): void
    }>();

</script>


<style lang="scss" scoped>

</style>
  