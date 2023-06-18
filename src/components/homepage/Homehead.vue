<template>
  <section class="homehead bg-gradient">
    <div class="container">
      <div class="title-container d-flex align-items-center justify-content-center">
        <h1 class="title mx-5">Gagnez du temps Ne cherchez plus</h1>
        <div class="omi-gif d-flex align-items-center justify-content-center" style="overflow-x: hidden; margin-left: 32px">
          <img src="@/assets/gifs/omi.gif"/>
        </div>
      </div>
    </div>
    <div class="round-section"></div>
  </section>
</template>

<script>
export default {
  name: 'Homehead',
}
</script>

<style scoped>
.homehead{
  height: 100vh;
}
.bg-gradient{
  background: linear-gradient(90deg, var(--purple) 0%, var(--blue) 99%)!important;
}
.title-container{
  height: calc(100vh - 100px);
}
.title{
  font-family: 'Como';
  font-weight: 700;
  font-size: 109.66px;
  color: white;
  text-align: center;
  z-index: 2;
}
.omi-gif{
  position: absolute;
  width: 100%;
  z-index: 1;
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