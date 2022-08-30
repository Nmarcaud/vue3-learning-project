<template>
    <div class="m-3 p-4 shop">
        <ShopProductList :products="products" />
    </div>
</template>


<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/productinterface';
    import ShopProductList from './ShopProductList.vue';

    defineProps<{
        products: ProductInterface[]
    }>()


</script>


<style lang="scss" scoped>
    .shop {
        overflow-y: auto;
    }
</style>
  