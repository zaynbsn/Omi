<template>
  <AboutHeader></AboutHeader>
  
  <section class="container">
    <div class="team d-flex flex-column justify-content-center align-items-center">
      <TitleGradient label="Notre équipe" left></TitleGradient>

      <div class="theo row align-items-center justify-content-center">
        <div class="nils-picture col-sm-4">
          <img src="@/assets/img/nils.png" alt="Nils Boisson, web developper">
        </div>

        <div class="content col-sm-8">
          <div class="content-title">
            <div class="name">Nils Boisson</div>
            <div class="job">Développeur</div>
          </div>

          <div class="content-description">
            <p>Rencontrez Nils Boisson, le maestro du clavier, le Picasso du code et l'épicurien des développeurs.</p>
            <p>Parfois, nous le surprenons à discuter avec ses ordinateurs en binaire, nous sommes assez sûrs qu'ils le comprennent et qu’ils entretient des relations charnelles avec ses derniers</p>
          </div>
        </div>
      </div>
      
      <div v-if="isMobile" class="theo row align-items-center justify-content-center">
        <div class="theo-picture col-sm-4">
          <img src="@/assets/img/theo.png" alt="Theo Langlade, web designer">
        </div>

        <div class="content col-sm-8">
          <div class="content-title">
            <div class="name">Theo Langlade</div>
            <div class="job">Designer</div>
          </div>

          <div class="content-description">
            <p>Voici Théo Langlade, notre designer charmeur aux biceps saillants. Quand il n'est pas en train de soulever des poids ou de faire battre les cœurs, il conçoit avec passion des produits aussi robustes que son physique.</p>
            <p>Connu pour transformer ses séances de musculation en brainstormings, Théo apporte à chaque produit une robustesse et un charme qui sont indéniablement les siens</p>
          </div>
        </div>
      </div>

      <div v-if="!isMobile" class="theo row align-items-center justify-content-center" style="margin-top: -7rem">
        <div class="content col-sm-8">
          <div class="content-title" style="justify-content: end;">
            <div class="job">Designer</div>
            <div class="name">Theo Langlade</div>
          </div>
          
          <div class="content-description" >
            <p>Voici Théo Langlade, notre designer charmeur aux biceps saillants. Quand il n'est pas en train de soulever des poids ou de faire battre les cœurs, il conçoit avec passion des produits aussi robustes que son physique.</p>
            <p>Connu pour transformer ses séances de musculation en brainstormings, Théo apporte à chaque produit une robustesse et un charme qui sont indéniablement les siens</p>
          </div>
        </div>

        <div class="theo-picture col-sm-4" style="position: relative; left:-192px; z-index:-1;">
          <img src="@/assets/img/theo.png" alt="Theo Langlade, web designer" >
          <!-- style="position: relative; left: -27%;" -->
        </div>
      </div>
      
      <div class="maddy row align-items-center justify-content-center" :style="!isMobile ? 'margin-top: -7rem' : ''">
        <div class="maddy-picture col-sm-4">
          <img src="@/assets/img/maddy.png" alt="Maddy Misto, web designer">
        </div>

        <div class="content col-sm-8">
          <div class="content-title">
            <div class="name">Maddy Misto</div>
            <div class="job">Designer</div>
          </div>

          <div class="content-description">
            <p>Décourez Maddy Misto, notre chef étoilé du design et reine de la cuisine. Sa passion pour la forme et la fonction se traduit dans chaque ligne d'Omi et chaque plat qu'elle concocte. </p>
            <p>Et si votre Omi sent légèrement la tarte aux pommes, ne vous inquiétez pas, c'est juste Maddy qui réfléchit à son prochain design... ou dessert!</p>
          </div>
        </div>
      </div>
    </div>
    <DontLoseTime style="position: relative; z-index: 2;"></DontLoseTime>
  </section>
</template>

<script>
import AboutHeader from '@/components/about/AboutHeader.vue'
import TitleGradient from '@/components/UI/TitleGradient.vue'
import DontLoseTime from '@/components/about/DontloseTime.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin'

export default {
  name: "About",
  components: { AboutHeader, TitleGradient, DontLoseTime },
  mixins: [ windowWidthMixin ]
}
</script>

<style scoped>
.content-title{
  display: flex;
  justify-content: start;
  align-items: center;
  margin-bottom: 32px
}
.name{
  background-color: var(--lavander);
  border-radius: 32px;
  padding: 12px 24px;
  font-family: 'Como';
  font-size: 24px;
  font-weight: 700;
  width: fit-content;
}
.job{
  padding: 16px 32px;
  font-family: 'Como';
  font-size: 16px;
  font-weight: 600;
  width: fit-content;
}

.content-description{
  padding-left: 96px;
  width: 75%;
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 16px;
}

@media screen and (max-width: 768px) {
  .content-title{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 32px
  }
}
</style>