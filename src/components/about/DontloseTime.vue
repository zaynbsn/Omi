<template>
  <section class="container">
      <div class="dont-lose-time bg-lavander d-flex flex-column justify-content-center align-items-center p-5 mx-3" :style="!isMobile ? 'margin: 128px 0;' : 'margin: 72px 0;'">
        <div class="d-flex flex-column justify-content-center align-items-center" :style="!isMobile ? 'width: 70%;' : ''">
          <h1 class="title mb-4">Ne perdez plus jamais de temps</h1>
          <h2 class="subtitle mb-3">à chercher vos clés ou votre portefeuille.</h2>
          <h2 class="subtitle mb-5">Omi est à un clic de distance.</h2>
          <SecondaryButton label="Simpifier mon quotidien avec Omi" black to="/product"></SecondaryButton>
        </div>
      </div>
    </section>
</template>

<script>
import SecondaryButton from '@/components/UI/SecondaryButton.vue'
import windowWidthMixin from '@/mixins/windowWidthMixin';

export default {
  name: 'DontLoseTime',
  components: { SecondaryButton },
  mixins: [ windowWidthMixin ],
}
</script>

<style scoped>
.dont-lose-time{
  border-radius: 32px;
}
.bg-lavander{
  background-color: var(--lavander);
}
.title{
  font-family: 'Como';
  font-weight: 700;
  font-size: 92px;
  color: black;
  text-align: center;
}
@media screen and (max-width: 768px) {
  .title{
    font-size: 48px;
  }
}

.subtitle {
  font-family: 'Como';
  font-weight: 500;
  font-size: 24px;
  color: white;
  text-align: center;
  color: black
}
</style>