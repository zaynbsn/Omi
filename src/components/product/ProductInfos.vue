<template>
  <section class="container">
    <div class="multifunction row justify-content-center my-5">
      <div v-if="!isMobile" class="col-sm-5 d-flex justify-content-start align-items-start">
        <img src="@/assets/img/defaultProduct.png" alt="default">
      </div>

      <div class="col-sm-5 d-flex flex-column justify-content-start align-items-start">
        <TitleGradient label="L'étagère multifonctions" left style="font-size: 42px!important; margin-bottom: 32px"></TitleGradient>

        <div class="texts">
          <div v-for="(text, index) in multiTexts" :key="index" class="text">
            <p>{{ text }}</p>
          </div>
        </div>

        <SecondaryButton v-if="!isMobile" label="Je choisi Omi" class="mt-4" to="/product"></SecondaryButton>
      </div>
    </div>

    <div class="smart row justify-content-center mb-5">
      <div class="col-sm-5 d-flex flex-column justify-content-start align-items-start">
        <TitleGradient label="Le boitier intelligent" left style="font-size: 42px!important; margin-bottom: 32px"></TitleGradient>

        <div class="texts">
          <div v-for="(text, index) in smartTexts" :key="index" class="text">
            <p>{{ text }}</p>
          </div>
        </div>

        <SecondaryButton v-if="!isMobile" label="Je choisi Omi" class="mt-4" to="/product"></SecondaryButton>
      </div>

      <div v-if="!isMobile" class="col-sm-5 d-flex justify-content-start align-items-start">
        <img src="@/assets/img/defaultProduct.png" alt="default">
      </div>
    </div>

    <div class="rfid row justify-content-center mb-5">
      <div v-if="!isMobile" class="col-sm-5 d-flex justify-content-start align-items-start">
        <img src="@/assets/img/defaultProduct.png" alt="default">
      </div>

      <div class="col-sm-5 d-flex flex-column justify-content-start align-items-start">
        <TitleGradient label="La technologie RFID" left style="font-size: 42px!important; margin-bottom: 32px"></TitleGradient>

        <div class="texts">
          <div v-for="(text, index) in rfidTexts" :key="index" class="text">
            <p>{{ text }}</p>
          </div>
        </div>

        <SecondaryButton label="Je choisi Omi" class="mt-4" to="/product"></SecondaryButton>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue'
import SecondaryButton from '@/components/UI/SecondaryButton.vue'
import Customization from '@/components/product/Customization.vue'
import TitleGradient from '@/components/UI/TitleGradient.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin'

export default {
  name: "ProductInfos",
  components: { SecondaryButton, Customization, TitleGradient },
  mixins: [ windowWidthMixin ],
  setup() {
    const multiTexts = ref([
      "Omi intègre une étagère intelligente et organisée pour vos essentiels. Elle comprend trois compartiments distincts pour vos clés de maison, de voiture et votre portefeuille, offrant un rangement ordonné. ",
      "Un miroir intégré ajoute une touche d'élégance et de fonctionnalité. ",
      "Ce qui distingue Omi, ce sont les LEDs intégrées à chaque compartiment, signalant la présence ou l'absence de l'objet correspondant.",
      "Plus besoin de fouiller pour trouver vos objets. Ils ont leur propre place, visible et à portée de main. Avec Omi, la gestion de vos essentiels devient intuitive, élégante et moderne.",
    ])
    const smartTexts = ref([
      "Le boîtier Omi, installé à votre porte, est l'extension parfaite de l'étagère, ajoutant une gestion intelligente de vos essentiels. Équipé de capteurs ultrasoniques, d'un accéléromètre et de LEDs, il transforme votre porte en veilleuse de vos objets indispensables. ",
      "Chaque LED est liée à un objet essentiel. Si vous sortez sans un de ces objets, la LED correspondante s'allume, vous avertissant avant de partir. À votre retour, le boîtier vous rappelle de déposer vos objets dans l'étagère par l'allumage des LEDs appropriées. ",
      "Omi, votre assistant personnel, vous aide à garder une trace de vos essentiels, offrant une tranquillité d'esprit en s'assurant qu'ils sont toujours là où ils doivent être.",
    ])

    const rfidTexts = ref([
      "Omi doit sa magie à la technologie RFID (Identification par Radio Fréquence), une innovation clé qui permet de suivre vos essentiels. ",
      "Chaque objet - clés de maison, clés de voiture et portefeuille - est doté d'une puce RFID, qui interagit avec des capteurs sur l'étagère Omi pour indiquer leur présence.",
      "Si vous sortez sans vos essentiels, les capteurs RFID le détectent et le boîtier allume la LED correspondante, vous signalant l'oubli. ",
      "Lorsque vous rentrez sans avoir encore déposé vos objets, le boîtier illumine les LEDs pour vous rappeler de le faire.",
      "La technologie RFID d'Omi agit automatiquement, sans action de votre part. Pas de boutons à presser, ni de codes à entrer. Omi allège le stress de la recherche d'objets perdus, pour une tranquillité d'esprit incomparable : vous savez toujours où sont vos essentiels.",
    ])

    return {multiTexts, smartTexts, rfidTexts}
  }
}
</script>

<style scoped>
.text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 14px;
}
p{
  margin-bottom: 8px;
}
</style>