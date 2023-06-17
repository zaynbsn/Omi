<template>
  <section class="container">
    <div class="nav-container d-flex justify-content-between align-items-center p-4">
      <router-link class="logo" to="/">
        <img src="@/assets/img/omiLogoColor.svg" alt="Omi logo">
      </router-link>

      <div class="nav row d-flex justify-content-center align-items-center">
        <router-link to="/product" class="link col">Notre Produit</router-link>
        <router-link to="/product" class="link col">À propos</router-link>
        <MainButton label="Acheter" to="/product"></MainButton>
      </div>
    </div>
  </section>
</template>

<script>

import MainButton from '@/components/UI/MainButton.vue';
export default {
    name: "Navbar",
    components: { MainButton }
}
</script>

<style scoped>
.link {
  color: var(--md-blue);
  text-decoration: none;
  width: fit-content;
  white-space: nowrap;
  border-radius: 8px;
  padding: 8px 16px;
  margin-right: 1rem;
}
.link:hover {
  background-color: #f3f3f3;
}
</style>