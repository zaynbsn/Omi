<template>
  <Customization></Customization>

  <ProductInfos></ProductInfos>

  <Tech></Tech>
</template>

<script>
import Customization from '@/components/product/Customization.vue'
import ProductInfos from '@/components/product/ProductInfos.vue';
import Tech from '@/components/product/Tech.vue';

export default {
    name: "Product",
    components: { Customization, ProductInfos, Tech }
}
</script>
