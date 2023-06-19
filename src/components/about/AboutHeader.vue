<template>
  <div class="about-header">
    <section class="container pb-5 mb-5">
      <div class="header-content d-flex flex-column justify-content-center align-items-center pt-5" style="width: 60%;">
        <div class="title">Qui sommes-nous ?</div>
        <div class="texts">
          <div v-for="(text, index) in texts" :key="index" class="text">
            <p>{{ text }}</p>
          </div>
        </div>
      </div>
    </section>
    <div class="round-section"></div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: "AboutHeader",
  components: {  },
  setup() {
    const texts = ref([
      "Nous sommes un trio d'étudiants dévoués de l'École des Gobelins, spécialisés dans le design de l'innovation numérique. ",
      "Passionnés par la possibilité d'améliorer la vie quotidienne grâce à la technologie, nous avons consacré notre projet de fin d'année à la création d'Omi, une solution innovante pour la gestion de vos objets du quotidien.",
      "Notre formation à l'École des Gobelins nous a dotés d'une expertise dans l'alliance de l'esthétique, de la fonctionnalité et de la technologie de pointe. Avec Omi, nous avons mis en œuvre ces compétences pour développer un produit qui simplifie votre routine quotidienne tout en apportant une touche de modernité à votre foyer.",
      "Omi incarne notre engagement à mettre en place des solutions de design intelligentes pour les défis de la vie quotidienne. C'est avec une immense fierté et beaucoup d'excitation que nous vous présentons Omi, la solution ultime pour rester organisé et sans stress.",
    ])
    
    return {texts}
  }
}
</script>

<style scoped>
.about-header{
  background-image: url('../../assets/img/aboutImage.jpg');
  background-size: cover;
}
.title{
  font-family: 'Como';
  font-weight: 700;
  font-size: 72px;
  color: white;
  text-align: center;
}
.text{
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 14px;
  color: white;
}
.round-section{
  width: 100%;
  background-color: white;
  border-radius: 96px 96px 0 0;
  height: 125px;
  margin-top: -24px;
}
@media screen and (max-width: 768px) {
  .title{
    font-size: 64px;
  }
  .round-section{
    height: 85px;
    margin-top: 15px;
  }
}
</style>