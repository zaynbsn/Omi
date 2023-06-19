<template>
  <section class="container">
    <div class="nav-container d-flex justify-content-between align-items-center p-4">
      <router-link class="logo" to="/">
        <img v-if="!isMobile" src="@/assets/img/omiLogoColor.svg" alt="Omi logo">
        <img v-if="isMobile" src="@/assets/img/omiLogoMin.svg" alt="Omi logo">
      </router-link>


      <div v-if="!isMobile" class="nav row d-flex justify-content-center align-items-center">
        <router-link to="/product" class="link col">Notre Produit</router-link>
        <router-link to="/about" class="link col">À propos</router-link>
        <MainButton label="Acheter" to="/product"></MainButton>
      </div>
      <div v-if="isMobile" class="burger-menu d-flex justify-content-center align-items-center">
        <img v-if="isNavbarMobileOpen" src="@/assets/img/cross.svg" alt="croix de fermeture du burger menu" @click="isNavbarMobileOpen = !isNavbarMobileOpen">
        <img v-else src="@/assets/img/burgerMenu.svg" alt="burger menu" @click="isNavbarMobileOpen = !isNavbarMobileOpen">
      </div>
    </div>
    <div v-if="isMobile" class="d-flex flex-column justify-content-center align-items-center" :class="isNavbarMobileOpen ? 'nav-mobile-on p-4' : 'nav-mobile-off'">
      <transition>
        <div v-if="isNavbarMobileOpen">
          <hr style="width: 100%;" />
          <router-link v-if="isNavbarMobileOpen" to="/product" class="link mb-3" >Notre Produit</router-link>
          <router-link v-if="isNavbarMobileOpen" to="/about" class="link mb-3">À propos</router-link>
          <div class="mb-5 d-flex justify-content-center align-items-center">
            <MainButton v-if="isNavbarMobileOpen" label="Acheter" to="/product" ></MainButton>
          </div>
        </div>
        
      </transition>
    </div>
  </section>
</template>

<script>
import windowWidthMixin from '@/mixins/windowWidthMixin'
import MainButton from '@/components/UI/MainButton.vue';

export default {
    name: "Navbar",
    components: { MainButton },
    mixins: [ windowWidthMixin ],
    data() {
      return {
        isNavbarMobileOpen: false
      }
    }
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
  transition: 1s;
  display: block;
  text-align: center;
}
@media screen and (max-width: 768px){
  .link {
    margin-right: 0;
    width: 200px;
  }
}

.v-enter-active, .v-leave-active {
  transition: opacity 2s;
}

.v-enter-from, .v-leave-to {
  opacity: 0;
  transition: 0.25s;
}
.link:hover {
  background-color: #f3f3f3;
}
.nav-mobile-off{
  height: 0;
  transition: 1s;
}
.nav-mobile-on{
  height: 200px;
  transition: 1s;
}
</style>