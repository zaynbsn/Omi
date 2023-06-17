<template>
  <section class="container-sm">
      <div class="about-container d-flex flex-column justify-content-center align-items-center" style="margin-top: 128px;">
        <div class="about-title" style="width: 80%;" >
          <TitleGradient label="Qui sommes-nous ?" left class="mb-4"></TitleGradient>
        </div>

        <div class="about-content d-flex justify-content-center align-items-center">
          <div class="content p-5">
            <div class="texts-container mb-5">
              <div v-for="(text, index) in texts" :key="index" class="text">
                <p>{{ text }}</p>
              </div>
            </div>

            <SecondaryButton label="Decouvrez-nous" class="mt-4" to="/product"></SecondaryButton>
          </div>

          <div class="image" style="margin-left: -128px">
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

export default {
  name: 'AboutUs',
  components: { TitleGradient, SecondaryButton },
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
}
.text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 14px;
  max-width: 70%;
}
</style>