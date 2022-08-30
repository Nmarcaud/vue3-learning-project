<template>
    <div class="grid p-3" >
        <ShopProduct v-for="product in products" :product="product"/>
    </div>
</template>


<script setup lang="ts">
    import ShopProduct from "./ShopProduct.vue";
    import type { ProductInterface } from '@/interfaces/productinterface';
    
    defineProps<{
        products: ProductInterface[]
    }>()

</script>

<style>
    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-auto-rows: auto;
        gap: 2rem
    }  
</style>
