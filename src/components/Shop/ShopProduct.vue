<template>
    <div class="card">
        <div class="card-body p-4 d-flex flex-column">
            <img class="img-fluid br-08 mb-3" :src="product.image" alt="">
            <h4 class="card-title">{{ product.title }}</h4>
            <p>{{ product.description }}</p>
            <div class="d-flex align-items-center mt-auto">
                <strong class="flex-fill">Prix : {{ product.price }}€</strong>
                <button class="btn btn-secondary" @click="emit('addProductToCart', product.id)">Buy it</button>
            </div>
        </div>
    </div>
</template>


<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces';
    
    defineProps<{
        product: ProductInterface
    }>();

    const emit = defineEmits<{
        (e: 'addProductToCart', productId: number): void
    }>();

</script>


<style lang="scss" scoped>
</style>
  