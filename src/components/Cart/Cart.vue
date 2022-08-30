<template>
    <div class="bg-white p-4">
        <h1>Cart</h1>
        <CartProductList :cart="cart" @remove-product-from-cart="emit('removeProductFromCart', $event)" />
    </div>
</template>


<script setup lang="ts">
    import type { ProductInterface } from "@/interfaces/productinterface";
    import CartProductList from "./CartProductList.vue";

    defineProps<{
        cart: ProductInterface[]
    }>();

    const emit = defineEmits<{
        (e: 'removeProductFromCart', productId: number): void
    }>();
</script>


<style lang="scss" scoped>
    
</style>
