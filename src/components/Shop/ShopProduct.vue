<template>
    <div class="card">
        <div class="card-body p-4">
            <img class="img-fluid br-08 mb-3" :src="product.image" alt="">
            <h4 class="card-title">{{ product.title }}</h4>
            <p>{{ product.description }}</p>
            <div class="d-flex align-items-center">
                <strong class="flex-fill">Prix : {{ product.price }}€</strong>
                <button class="btn btn-secondary">Buy it</button>
            </div>
        </div>
    </div>
</template>


<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/productinterface';
    
    defineProps<{
        product: ProductInterface
    }>()
</script>


<style lang="scss" scoped>
</style>
  