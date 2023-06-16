<template>
    <Homehead></Homehead>

    <Reviews></Reviews>

    <Product></Product>

    <AboutUs></AboutUs>
    
    <DontLoseTime></DontLoseTime>

    <Renaissance></Renaissance>

    <Faq></Faq>
    
</template>

<script>
import { ref } from 'vue'
import Homehead from '@/components/homepage/Homehead.vue' 
import Reviews from '@/components/homepage/Reviews.vue'
import Product from '@/components/homepage/Product.vue'
import AboutUs from '@/components/homepage/AboutUs.vue'
import DontLoseTime from '@/components/homepage/DontloseTime.vue'
import Renaissance from '@/components/homepage/Renaissance.vue'
import Faq from '@/components/homepage/Faq.vue'
import TitleGradient from '@/components/UI/titleGradient.vue'
import SecondaryButton from '@/components/UI/SecondaryButton.vue'

export default {
  name: 'Homepage',
  components: { Homehead, Reviews, Product, AboutUs, DontLoseTime, Renaissance, Faq, TitleGradient, SecondaryButton },
}
</script>