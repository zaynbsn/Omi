<template>
  <section class="container">
      <div class="product-container row" :class="!isMobile ? 'px-5' : 'mt-5'" :style="!isMobile ? 'margin: 128px 0;' : 'margin-left: 10px;'">
        <div v-if="!isMobile" class="product-image col-6 d-flex align-items center justify-content-center " >
          <img src="@/assets/img/baseImage.png" alt="omi product" style="object-fit: contain; margin: 0 2rem 0 2rem; max-width: 100%"  >
        </div>

        <div v-if="!isMobile" class="product-content col-6 row">
          <TitleGradient label="Notre Produit" left class="mb-4"></TitleGradient>
          
          <div v-for="(text, index) in texts" :key="index" class="text">
            <p>{{ text }}</p>
          </div>
          
          <SecondaryButton label="Voir toutes les fonctionnalitées" class="mt-4" to="/product"></SecondaryButton>
        </div>
        
        <div v-if="isMobile" class="product-content row">
          <TitleGradient label="Notre Produit" class="mb-3"></TitleGradient>

          <div class="mobile-div" style="position: relative;">
            <img src="@/assets/img/mobileProduct.png" alt="mobile product" style="width: 100%;" />
            <div class="mobile-texts p-4" style="position: absolute; top: 12%; color: white;">
              <div v-for="(text, index) in mobileTexts" :key="index" class="text">
                <p>{{ text }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
import { ref } from 'vue'
import TitleGradient from '@/components/UI/TitleGradient.vue'
import SecondaryButton from '@/components/UI/SecondaryButton.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin'

export default {
  name: 'Product',
  components: { TitleGradient, SecondaryButton },
  mixins: [ windowWidthMixin ],
  setup() {
    const texts = ref([
      "Bienvenue dans l'ère de l'organisation intelligente. Découvrez Omi, une solution innovante conçue pour simplifier votre quotidien.",
      "Conçu avec soin, Omi n'est pas simplement un outil fonctionnel, mais aussi un élément esthétique qui apporte une touche de modernité à votre intérieur. Muni d'un miroir intégré, il allie style et fonctionnalité pour s'adapter à tout type de décoration.",
      "Au cœur de notre produit se trouve l'étagère avec ses trois compartiments dédiés. Chacun est conçu pour accueillir un objet spécifique : vos clés de maison, vos clés de voiture et votre portefeuille. Chaque compartiment est associé à une LED unique qui indique la présence ou l'absence de l'objet correspondant",
      "Associé à cette étagère, un boîtier intelligent est installé sur votre porte d'entrée. Ce boîtier est équipé d'un système de détection à ultrasons et d'un accéléromètre pour identifier les mouvements de la porte.",
      "Omi est conçu pour rendre votre quotidien plus fluide et organisé. Il vous assure que vos essentiels sont toujours là où vous en avez besoin. Il élimine le stress de la recherche de vos objets perdus et vous donne la tranquillité d'esprit pour commencer ou terminer votre journée.",
      "Embrassez la simplicité, embrassez l'organisation, embrassez le futur avec notre Vide Poche Connecté.",
    ])
    const mobileTexts = ref([
      "Embarquez dans l'ère de l'organisation intelligente avec Omi, notre solution innovante pour simplifier votre quotidien. ",
      "Omi, plus qu'un outil fonctionnel, est un ajout esthétique à votre intérieur, combinant style et fonctionnalité avec son miroir intégré. Son étagère comporte trois compartiments dédiés à vos clés et portefeuille, chacun avec une LED signalant leur présence. ",
      "Un boîtier intelligent, équipé de détection ultrasonique, est installé sur votre porte pour capter les mouvements. ",
      "Omi rend votre quotidien plus fluide, assure la disponibilité de vos essentiels et élimine le stress de la recherche d'objets perdus. Avec Omi, embrassez une vie simplifiée, organisée et futuriste.",
    ])

    return {texts, mobileTexts}
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