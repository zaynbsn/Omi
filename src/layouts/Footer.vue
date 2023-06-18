<template>
  <section class="footer-container">
    <div class="footer-content d-flex flex-column justify-content-center align-items-center ">
      <img src="@/assets/img/omiLogo.svg" alt="omi logo">
      <div class="product link my-4">Notre produit</div>
      <div class="team link mb-4">Notre équipe</div>
      <div class="buy link mb-4">Acheter Omi</div>
      <div class="conditions mb-4">Politique de confidentialité & Conditions d’utilisations</div>
      <div class="socials d-flex justify-content-around align-items-center">
        <img src="@/assets/img/instagram.svg" alt="instagram logo" style="margin: 0 1rem;">
        <img src="@/assets/img/linkedin.svg" alt="linkedin logo" style="margin: 0 1rem;">
        <img src="@/assets/img/facebook.svg" alt="facebook logo" style="margin: 0 1rem;">
      </div>
    </div>
  </section>
</template>

<script>

export default {
  name: 'Footer',
}
</script>

<style>
body{
  overflow-x: hidden;
}
.footer-container {
  width: 120vw;
  height: 100vh;
  overflow-x: hidden;
  background: linear-gradient(90deg, var(--purple) 0%, var(--blue) 99%)!important;
  border-radius: 100% 100% 0 0;
  margin-left: calc(50% - 60vw);
  margin-top: -25vh;
  color: white;
}
.footer-content {
  width: 50vw;
  margin-left: calc(50% - 25vw);
  margin-top: 35vh;
  height: fit-content;
}
.link{
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 16px;
}
.conditions {
  font-family: 'Montserrat', sans-serif;
  font-weight: 400;
  font-size: 9.89px;
  text-decoration: underline;
}

@media screen and (max-width: 768px){
  .footer-container {
    width: 200vw;
    height: 90vh;
    background: linear-gradient(90deg, var(--purple) 25%, var(--blue) 75%)!important;
    margin-left: calc(50% - 100vw);
  }
  .footer-content {
    width: 50vw;
    margin-left: calc(50% - 25vw);
    margin-top: 30vh;
    height: fit-content;
  }
}
</style>
