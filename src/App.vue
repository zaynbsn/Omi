<template>
  <Navbar></Navbar>

  <RouterView />

  <Footer></Footer>
</template>

<script setup>
import { RouterView } from 'vue-router'
import Navbar from '@/layouts/Navbar.vue';
import Footer from '@/layouts/Footer.vue'
</script>