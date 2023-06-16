<template>
  <section class="container">
      <div class="renaissance d-flex flex-column justify-content-center align-items-center mb-5">
        <div class="my-4">
          <TitleGradient label="En partenariat avec la Re-Naissance"></TitleGradient>
        </div>
        <div class="content-container row p-5">
          <div class="texts col-6">
            <div v-for="(text, index) in texts" :key="index" class="text">
              <p>{{ text }}</p>
            </div>
          </div>

          <div class="logo-container col-6 d-flex justify-content-center align-items-center">
            <img src="@/assets/img/renaissance.svg" alt="logo association Re-Naissance" style="width: 80%">
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
  name: 'Renaissance',
  components: { TitleGradient, SecondaryButton },
  setup() {
    const texts = ref([
      "Omi a été conçu en étroite collaboration avec 'Renaissance 74', une association dédiée à l'accompagnement des personnes atteintes de cérébrolésion acquise, et qui affrontent quotidiennement des défis tels que les troubles de motricité, de parole, cognitifs et de mémoire. ",
      "C'est avec l'objectif de répondre aux besoins spécifiques de ces personnes que nous avons construit Omi. Ce n'est pas simplement un produit pour elles, mais un produit réalisé avec elles.",
      " Ce partenariat avec l’association a guidé chaque étape de notre processus de conception, enracinant notre engagement à améliorer la qualité de vie par l'innovation. ",
      "Notre collaboration avec 'Renaissance 74' est la force qui a rendu Omi possible, et nous en sommes extrêmement fiers."
    ])

    return {texts}
  }
}
</script>

<style scoped>
.content-container{
  background-color: var(--lavander);
  border-radius: 32px;
}
.text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 16px;
}
.logo-container{
  background-color: var(--dk-blue);
  border-radius: 32px;
}

</style>