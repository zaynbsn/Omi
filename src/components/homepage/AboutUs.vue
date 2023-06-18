<template>
  <section class="container-sm">
      <div class="about-container d-flex flex-column justify-content-center align-items-center mx-3"  :style="!isMobile ? 'margin: 128px 0;' : 'margin: 64px 0;'">
        <div class="about-title" style="width: 80%;" >
          <TitleGradient label="Qui sommes&#8209;nous&#160;?" :left="isMobile ? false : true" class="mb-4"></TitleGradient>
        </div>

        <div class="about-content d-flex justify-content-center align-items-center" :class="isMobile ? 'flex-column' : ''">
          <div class="content p-sm-5" style="padding: 32px;">
            <div class="texts-container mb-5">
              <div v-for="(text, index) in texts" :key="index" class="text">
                <p>{{ text }}</p>
              </div>
            </div>

            <SecondaryButton v-if="!isMobile" label="Decouvrez-nous" class="mt-4" to="/product"></SecondaryButton>
            
            <div v-if="isMobile" class="image-mobile">
              <img src="@/assets/img/aboutImage.png" alt="about image">
            </div>
          </div>
          
          <SecondaryButton v-if="isMobile" label="Decouvrez-nous" class="mt-4" to="/product"></SecondaryButton>
          
          <div v-if="!isMobile" class="image" style="margin-left: -128px">
            <img src="@/assets/img/aboutImage.png" alt="about image">
          </div>
        </div>
      </div>
    </section>
</template>

<script>
import { ref } from 'vue'
import TitleGradient from '@/components/UI/titleGradient.vue'
import SecondaryButton from '@/components/UI/SecondaryButton.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin'

export default {
  name: 'AboutUs',
  components: { TitleGradient, SecondaryButton },
  mixins: [ windowWidthMixin ],
  setup() {
    const texts = ref([
      "Nous sommes trois étudiants en design d'innovation numérique à l'École des Gobelins. ",
      "Passionnés par l'amélioration du quotidien à travers la technologie, nous avons créé Omi pour notre projet de fin d'année.",
      "Omi est le fruit de notre expertise, combinant esthétique, fonctionnalité et innovation pour une gestion optimale de vos objets essentiels.",
      "C'est avec fierté que nous vous présentons Omi, une solution de rangement intelligente qui transforme votre quotidien.",
    ])

    return {texts}
  }
}
</script>

<style scoped>
.content{
  background-color: var(--md-blue);
  border-radius: 32px;
  color: white;
  max-width: 90vw;
}
.text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 14px;
  max-width: 70%;
}
@media screen and (max-width: 768px){
  .text {
    max-width: 100vw;
    width: fit-content;
  }
}
.image-mobile {
  width:100%;
  height: auto;
}
.image-mobile img {
  width:100%;
  height: auto;
}
</style>