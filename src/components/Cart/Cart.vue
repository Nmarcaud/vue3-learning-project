<template>
    <div class="bg-white p-4 d-flex flex-column">
        <h1>Cart</h1>
        <CartProductList 
            class="flex-fill"
            :cart="cart" 
            @remove-product-from-cart="emit('removeProductFromCart', $event)" />
        <button class="btn btn-success">Commander {{ totalPrice }}€</button>
    </div>
</template>


<script setup lang="ts">
    import type { ProductCartInterface } from "@/interfaces";
    import { computed } from "vue";
    import CartProductList from "./CartProductList.vue";

    const props = defineProps<{
        cart: ProductCartInterface[]
    }>();

    const totalPrice = computed(() => props.cart.reduce((acc, product) => {
        return acc + product.quantity * product.price
    }, 0 ));

    const emit = defineEmits<{
        (e: 'removeProductFromCart', productId: number): void
    }>();

</script>


<style lang="scss" scoped>
    
</style>
