<template>
    <div class="card mb-3 bg-lg-1 br-10 p-4">
        <div class="d-flex justify-content-between align-items-center">
            <strong> {{ product.title }}</strong>
            <button class="btn btn-sm btn-danger" @click="emit('removeProductFromCart', product.id)">Suppr</button>
        </div>
        <div class="d-flex justify-content-between align-items-center">
            <p class="mb-0 dg-1">Quantité : 2 | Prix : {{ product.price }}€</p>
            <strong class="mb-0">Total : 3 000€</strong>
        </div>
    </div>
    
</template>


<script setup lang="ts">
import type { ProductInterface } from '@/interfaces/productinterface';

    defineProps<{
        product: ProductInterface
    }>();

    const emit = defineEmits<{
        (e: 'removeProductFromCart', productId: number): void
    }>();

</script>


<style lang="scss" scoped>
</style>
  