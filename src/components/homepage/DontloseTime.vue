<template>
  <section class="container">
      <div class="dont-lose-time bg-gradient d-flex flex-column justify-content-center align-items-center p-5 my-4">
        <div class="d-flex flex-column justify-content-center align-items-center" style="width: 70%;">
          <h1 class="title mb-5">Ne perdez plus jamais de temps</h1>
          <h2 class="subtitle  mb-5">à chercher vos clés ou votre portefeuille. Omi est à un clic de distance.</h2>
          <SecondaryButton label="Simpifier mon quotidien avec Omi" black></SecondaryButton>
        </div>
      </div>
    </section>
</template>

<script>
import SecondaryButton from '@/components/UI/SecondaryButton.vue'

export default {
  name: 'DontLoseTime',
  components: { SecondaryButton },
}
</script>

<style scoped>
.dont-lose-time{
  border-radius: 32px;
}
.bg-gradient{
  background: linear-gradient(90deg, var(--purple) 0%, var(--blue) 99%)!important;
}
.title{
  font-family: 'Como';
  font-weight: 700;
  font-size: 92px;
  color: white;
  text-align: center;
}
.subtitle {
  font-family: 'Como';
  font-weight: 700;
  font-size: 24px;
  color: white;
  text-align: center;
  color: black
}
</style>